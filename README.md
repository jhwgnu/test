##Part1. 위치 정보를 커널 내부에 추가

1. 위치 정보를 담고 있는 gps_location 구조체 추가
1868997673ca29265651d76d12b68fce9cf73c39

2. gps_location 구조체의 필드값을 변경할 수 있는 set_gps_location syscall 추가

3. gpsupdate.c 에서 이 syscall을 호출


##Part2. gps_location 구조체를 ext2 inode와 연동시키기

1. inode에 위치정보 필드 추가
https://github.com/swsnu/os-team19/commit/177b2022fd3c52f9bd4325a9031dae7438f5c680

2. inode operation에 set, get 함수 추가