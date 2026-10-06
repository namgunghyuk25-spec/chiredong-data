# 치레동 아카이브 월드 데이터

VRChat 월드 "치레동 아카이브"가 접속할 때 읽는 파일입니다. 월드에는 업로드 시점 사본이 들어 있고, 이 저장소의 `data.json`이 있으면 그걸로 덮어씁니다(재업로드 없이 갱신).

- 월드가 읽는 주소: `https://namgunghyuk25-spec.github.io/chiredong-data/data.json`
- 5회 줄 새 참가자 헬멧 리버리: `liv/r5_01.png` … `liv/r5_15.png` (벽 5회 줄 칸 순서, 2048×1024 albedo)

## 회차 결과 갱신

1. 방 폴더 `blueprint/rosters.json`의 해당 회차(drivers·winners·podium·date·win_label·mvp·champion)를 채운다.
2. `python ../make_world_data.py` → `data.json` 다시 생성(자체검사 포함).
3. 새 참가자 리버리가 있으면 `helmet_colors` 파이프라인으로 만든 albedo를 `liv/r5_NN.png`로 두고 다시 생성(파일이 있는 칸만 `livery: true`).
4. 이 폴더를 커밋·푸시 → 1~2분 뒤 Pages 반영, 다음 접속부터 월드에 보임.

## 한계

- 동적 칸은 5회 줄 15칸뿐. 6회부터는 칸·플라크를 월드에 추가하고 재업로드해야 함.
- 1~4회 헬멧·이름표·플라크는 월드에 구워져 있음(수정은 재업로드).
