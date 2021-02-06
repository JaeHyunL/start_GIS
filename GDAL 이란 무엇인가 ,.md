# GDAL 부셔버리기 ;

공부하면서 정리한거기에 개념이 틀리거나 다를 수 있습니다. 

인지하면서 보시기 바랍니다 ;





일단

#### GDAL 이란 무엇인가,

- GDAL(Geospatial data Abstraction Libray) 이며 지리정보 데이터 추상화 라이브러리 라는 뜻

- GDAL 은 C나 C++ 로 되어있지만 파이썬으로 바인딩이 가능합니다 



#### GDAL 커맨드 정리

**1) gdalinfo 해당 파일에 메타데이터 들을 확인 할 수 있습니다.**

ex) gdalinfo example.tif

옵션 

- -json : 출력을 json형식으로 
- -mm : 데이터 세트의 각 밴드에 대한 실제 최소 / 최대 값을 강제로 계산합니다 
- -stats  :  이미지 통계를 읽고 표시합니다. 이미지에 통계가 저장되지 않은 경우 강제 계산.
- -approx_stats : 이미지 통계를 읽고 표시합니다. 이미지에 통계가 저장되지 않은 경우 강제 계산.  모든 타일의 하위 집합을 기반으로 계산됨 그러나 정확하지 않은 경우 생김 
- -hits : 모든 밴드에 대한 히스토그램 정보를 보고합니다.
- -nogcp : 지상 기준점 목록 인쇄를 적제합니다. 

- -nomd : 메타 데이터 인쇄를 억제합니다. 일부 데이터 세트에는 많은 메타 데이터 문자열이 포함될 수 있습니다.
- -noct : 색상 표 인쇄를 억제합니다.
- -mdd : <domain>|all 다음을 사용하여 메타데이터를 추가합니다. 

- -nofl : 파일 목록의 첫 번째 파일 만 표시합니다. 

파일 형식 출력 

```t
Driver: GTiff/GeoTIFF
Files: (B040)??났?ъ쭊_202005501C00300019.tif
       (B040)??났?ъ쭊_202005501C00300019.tif.aux.xml
       (B040)??났?ъ쭊_202005501C00300019.wld
Size is 13824, 7680
Origin = (0.000000000000000,0.000000000000000)
Pixel Size = (1.000000000000000,1.000000000000000)
Image Structure Metadata:
  INTERLEAVE=PIXEL
Corner Coordinates:
Upper Left  (   0.0000000,   0.0000000)
Lower Left  (       0.000,    7680.000)
Upper Right (   13824.000,       0.000)
Lower Right (   13824.000,    7680.000)
Center      (    6912.000,    3840.000)
Band 1 Block=13824x1 Type=Byte, ColorInterp=Red
  Min=0.000 Max=255.000
  Minimum=0.000, Maximum=255.000, Mean=83.794, StdDev=42.708
  Metadata:
    STATISTICS_MAXIMUM=255
    STATISTICS_MEAN=83.793651891638
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=42.708177140122
    STATISTICS_VALID_PERCENT=100
Band 2 Block=13824x1 Type=Byte, ColorInterp=Green
  Min=0.000 Max=255.000
  Minimum=0.000, Maximum=255.000, Mean=83.689, StdDev=41.957
  Metadata:
    STATISTICS_MAXIMUM=255
    STATISTICS_MEAN=83.688757258286
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=41.956793159122
    STATISTICS_VALID_PERCENT=100
Band 3 Block=13824x1 Type=Byte, ColorInterp=Blue
  Min=0.000 Max=255.000
  Minimum=0.000, Maximum=255.000, Mean=81.544, StdDev=35.863
  Metadata:
    STATISTICS_MAXIMUM=255
    STATISTICS_MEAN=81.543956445765
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=35.862762310835
    STATISTICS_VALID_PERCENT=100
```



**2) gdal_translate 래스터 레이어를 다른 형식으로 변환합니다. ** 

ex) gdal_translate input output 

옵션

- -ot <type> : 다음 중 하나에 특정 데이터 형식을 갖는 출력 화상 밴드 강제 [Byte , Uint16 , Int16 , Uint32 , Int32 , Float32 , Float64 , CInt16, CInt32, CFloat32, CFloat64]
- -strict : 출력 형식으로 변환 할 때 손실 이 잃어나면 출력 억제 
- -if <format> : 입력 파일을 열기 위해 시도 할 형식 / 드라이버 이름입니다. 일반적으로 지정할 필요는 없지만 적절한 드라이버를 선택하지 못한 경우 자동 드라이버 검색을 건너 뛰는데 사용 할 수 있습니다. 이 옵션을 여러 번 반복하여 여러 후보 드라이버를 지정할 수 있습니다.
- -of <format> : 출력 형식을 선택 
- -a_srs <srs_def> : 출력 파일에 대한 투영을 재 정의합니다. Ex) EPSG:4326





**3) gdalwarp 재투영 워핑 유틸리티 모든 투영에 재 투영 할 수 있으며 이미지가 제어 정보가 있는 원시 인경우 이미지와 함께 저장된 GCP를 적용 할 수도 있습니다.**

옵션

- -s_srs <srs_def>  소스공간에 참조를 설정 ( source)
- -t_srs <srs_def>  대상 공간 참조를 설정합니다 (target)

- -ct <string> POJR 문자열 (단일 단계 작업 또는 + proj = pieline 으로 시작하는 다중 단계 문자열), CoordinateOperation 을 설명하는 WTK2 문자열 



기타등등 , 







참조 

https://en.wikipedia.org/wiki/GDAL

https://hgko1207.github.io/2020/03/26/satellite-gdal/

https://gdal.org/

https://gdal.org/programs/gdalinfo.html