#  MeshDataTool  
####**Inherits:** [Reference](class_reference)
####**Category:** Core

###  Brief Description  


###  Member Functions 
  * void  **[clear](#clear)**  **(** **)**
  * [int](class_int)  **[create&#95;from&#95;surface](#create_from_surface)**  **(** [Object](class_object) mesh, [int](class_int) surface  **)**
  * [int](class_int)  **[commit&#95;to&#95;surface](#commit_to_surface)**  **(** [Object](class_object) mesh  **)**
  * [int](class_int)  **[get&#95;format](#get_format)**  **(** **)** const
  * [int](class_int)  **[get&#95;vertex&#95;count](#get_vertex_count)**  **(** **)** const
  * [int](class_int)  **[get&#95;edge&#95;count](#get_edge_count)**  **(** **)** const
  * [int](class_int)  **[get&#95;face&#95;count](#get_face_count)**  **(** **)** const
  * void  **[set&#95;vertex](#set_vertex)**  **(** [int](class_int) idx, [Vector3](class_vector3) vertex  **)**
  * [Vector3](class_vector3)  **[get&#95;vertex](#get_vertex)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;vertex&#95;normal](#set_vertex_normal)**  **(** [int](class_int) idx, [Vector3](class_vector3) normal  **)**
  * [Vector3](class_vector3)  **[get&#95;vertex&#95;normal](#get_vertex_normal)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;vertex&#95;tangent](#set_vertex_tangent)**  **(** [int](class_int) idx, [Plane](class_plane) tangent  **)**
  * [Plane](class_plane)  **[get&#95;vertex&#95;tangent](#get_vertex_tangent)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;vertex&#95;uv](#set_vertex_uv)**  **(** [int](class_int) idx, [Vector2](class_vector2) uv  **)**
  * [Vector2](class_vector2)  **[get&#95;vertex&#95;uv](#get_vertex_uv)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;vertex&#95;uv2](#set_vertex_uv2)**  **(** [int](class_int) idx, [Vector2](class_vector2) uv2  **)**
  * [Vector2](class_vector2)  **[get&#95;vertex&#95;uv2](#get_vertex_uv2)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;vertex&#95;color](#set_vertex_color)**  **(** [int](class_int) idx, [Color](class_color) color  **)**
  * [Color](class_color)  **[get&#95;vertex&#95;color](#get_vertex_color)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;vertex&#95;bones](#set_vertex_bones)**  **(** [int](class_int) idx, [IntArray](class_intarray) bones  **)**
  * [IntArray](class_intarray)  **[get&#95;vertex&#95;bones](#get_vertex_bones)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;vertex&#95;weights](#set_vertex_weights)**  **(** [int](class_int) idx, [RealArray](class_realarray) weights  **)**
  * [RealArray](class_realarray)  **[get&#95;vertex&#95;weights](#get_vertex_weights)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;vertex&#95;meta](#set_vertex_meta)**  **(** [int](class_int) idx, var meta  **)**
  * void  **[get&#95;vertex&#95;meta](#get_vertex_meta)**  **(** [int](class_int) idx  **)** const
  * [IntArray](class_intarray)  **[get&#95;vertex&#95;edges](#get_vertex_edges)**  **(** [int](class_int) idx  **)** const
  * [IntArray](class_intarray)  **[get&#95;vertex&#95;faces](#get_vertex_faces)**  **(** [int](class_int) idx  **)** const
  * [int](class_int)  **[get&#95;edge&#95;vertex](#get_edge_vertex)**  **(** [int](class_int) idx, [int](class_int) vertex  **)** const
  * [IntArray](class_intarray)  **[get&#95;edge&#95;faces](#get_edge_faces)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;edge&#95;meta](#set_edge_meta)**  **(** [int](class_int) idx, var meta  **)**
  * void  **[get&#95;edge&#95;meta](#get_edge_meta)**  **(** [int](class_int) idx  **)** const
  * [int](class_int)  **[get&#95;face&#95;vertex](#get_face_vertex)**  **(** [int](class_int) idx, [int](class_int) vertex  **)** const
  * [int](class_int)  **[get&#95;face&#95;edge](#get_face_edge)**  **(** [int](class_int) idx, [int](class_int) edge  **)** const
  * void  **[set&#95;face&#95;meta](#set_face_meta)**  **(** [int](class_int) idx, var meta  **)**
  * void  **[get&#95;face&#95;meta](#get_face_meta)**  **(** [int](class_int) idx  **)** const
  * [Vector3](class_vector3)  **[get&#95;face&#95;normal](#get_face_normal)**  **(** [int](class_int) idx  **)** const
  * void  **[set&#95;material](#set_material)**  **(** [Material](class_material) material  **)**
  * [Object](class_object)  **[get&#95;material](#get_material)**  **(** **)** const

###  Member Function Description  
