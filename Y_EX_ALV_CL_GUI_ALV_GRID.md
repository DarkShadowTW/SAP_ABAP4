*--Purpose : This program shows how to use CL_GUI_ALV_GRID create gui alv in report

*--Author  : Eric Yang

*--DATE    : 2021/10/02

## For some information, please refer to Y_EX_ALV_EXAMPLE.md first 
## Please refer to the complete code ： Y_EX_ALV_CL_GUI_ALV_GRID

*--Demonstrate how to use GRID ALV

![This is a alt text.](/images/Y_EX_ALV_CL_GUI_ALV_GRID_000.png "GRID ALV DEMO")

*--Create Screen 0100 & set customer control object in this screen

![This is a alt text.](/images/Y_EX_ALV_CL_GUI_ALV_GRID_001.png "GRID ALV DEMO")

*--Default status, title & user command code in screen 0100

![This is a alt text.](/images/Y_EX_ALV_CL_GUI_ALV_GRID_002.png "GRID ALV DEMO")

*--Declare customer control object

DATA: w_con1_0100 TYPE REF TO cl_gui_custom_container.  "container object

*--initial & create object In Screen 0100 Flow logic MODULE init_obj

![This is a alt text.](/images/Y_EX_ALV_CL_GUI_ALV_GRID_003.png "GRID ALV DEMO")

*--Get Data from Table into internal Table

1. DATA: wt_ytsaber001 TYPE TABLE OF ytsaber001.

2. PERFORM f_getdata TABLES wt_ytsaber001.

*--Initial GRID ALV & Create ALV object & Link to Internal Tabe

1. DATA: gs_layout TYPE lvc_s_layo.
   DATA: w_alv_grid1_0100 TYPE REF TO cl_gui_alv_grid.     "ALV object
   
2. MODULE init_obj.

![This is a alt text.](/images/Y_EX_ALV_CL_GUI_ALV_GRID_004.png "GRID ALV DEMO")

*--After Call Screen 0100 & free GRID ALV object

  CALL METHOD w_alv_grid1_0100->free

  CALL METHOD w_con1_0100->free
  
![This is a alt text.](/images/Y_EX_ALV_CL_GUI_ALV_GRID_005.png "GRID ALV DEMO")

*--主意 Grid ALV 不能拋 Background Mode (要改 Function ALV / SALV)

![This is a alt text.](/images/Y_EX_ALV_CL_GUI_ALV_GRID_006.png "GRID ALV DEMO")
