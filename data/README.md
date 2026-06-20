# Data Directory

이 폴더는 실행에 필요한 원본/중간/결과 데이터를 두는 위치입니다.

일부 데이터는 서울시 빅데이터 캠퍼스 및 공공기관 데이터 반출 정책상 GitHub에 공개하지 않습니다. 저장소에는 데이터 대신 필요한 파일 구조와 파일명을 문서화합니다.

## Expected Structure

```bash
data/
├── final_score_4.csv
├── final_moa_recommend.csv
├── moa_center.csv
├── HVI_all/
├── HVI_final/
├── hdong_data/
│   └── bnd_dong_11_2025_2Q/
│       ├── bnd_dong_11_2025_2Q.shp
│       ├── bnd_dong_11_2025_2Q.shx
│       ├── bnd_dong_11_2025_2Q.dbf
│       └── ...
└── output/
```

## Key Inputs

- `final_score_4.csv`: HVI, Demand, Supply Gap을 통합한 행정동 단위 최종 지표
- `final_moa_recommend.csv`: 최종 제안 14개 행정동
- `moa_center.csv`: 기존 모아센터 위치 정보. `name`, `lat`, `lon` 컬럼 필요
- `hdong_data/`: 서울시 행정동 경계 shapefile
- `HVI_all/`, `HVI_final/`: HVI 산출 및 시각화용 중간 데이터

## Additional Restricted Data

일부 HVI 필터링 과정은 저장소 루트의 `Index_data/B068_HVI.csv`를 참조합니다.

```bash
Index_data/
└── B068_HVI.csv
```

이 데이터 역시 공개 제한이 있을 수 있으므로 필요 시 로컬에만 배치해서 사용합니다.

## Outputs

실행 결과는 `data/output/`에 저장됩니다.

```bash
data/output/
├── candidate_pool.csv
├── filter_log.txt
├── simulation_result.csv
├── coverage_score_result.csv
├── simulation_summary.txt
└── figures/
```
