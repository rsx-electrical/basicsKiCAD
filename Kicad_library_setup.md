# Kicad Installation + Libraries Setup


> 1. Download [KiCad](https://www.kicad.org/download) onto your local computer (download the most updated please -> ver. 9.0.4)
> 2. Install KiCad 
>    a. Next -> Next -> Next -> Install
>    b. Move to next step while we wait
> 3. Clone this repository onto your local computer: [rsx_standard_library](https://github.com/rsx-electrical/rsx_standard_library)
>    a. Download [Git](https://git-scm.com)
>    b. Install git. Here's a [guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
>      2.b1 Here's an easier guide for windows, watch until 1:14. [https://www.youtube.com/watch?v=iYkLrXobBbA](https://www.youtube.com/watch?v=iYkLrXobBbA)
>    c. In git bash: (fill in the < >)
```bash
cd <my_directory>
git clone https://github.com/rsx-electrical/rsx_standard_library.git
```
>   d. if you ```ls rsx_standard_library```, you should see:
```bash
$ ls rsx_standard_library
README.md  rsx_3d/  rsx_footprints/  rsx_syms/
```
> 4. Open Kicad when the installation is done
> 5. Import symbol library
>     a. Open Symbol Editor
>     b. Preferences -> Manage Symbol Libraries -> Add existing library to table
>     c. Select all the .sym files in ```<my_directory>/rsx_standard_library/rsx_syms``` -> Open
> 6. Go to KiCad homepage
> 7. Import footprint library
>     a. Open Footprint Editor
>     b. Preferences -> Manage Footprint Libraries -> Add Existing
>     c. Select all the .pretty folders in ```<my_directory>/rsx_standard_library/rsx_footprints``` -> Open
> 8. Add 3D models (we're still in Footprint Editor)
>     a. Preferences -> Configure Paths -> +    
>     b. add the absolute path of ```<my_directory>/rsx_standard_library/rsx_3d```

| Name          | path          |
| ------------- | ------------- |
| RSX_3D_LIB  | <my_directory>/rsx_standard_library/rsx_3d  |



