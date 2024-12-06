# <[위데이터랩] 1206 허깅페이스세미나 참여>

### 강의 주요 내용

- 1byte / Parameter
    - 32-bit 부동 소수점(Floating Point 32) 기준 
        - 1B 파라미터 * 4byte = 4GB
    - 8-bit 양자화 기준
        - 1B 파라미터 * 1byte = 1GB

- BP 방식의 토크나이저
    - BPE(byte pair encoding) : 
        1. 텍스트를 개별 문자로 분리
        2. 자주 등장하는 문자쌍들은 더큰 단위로
        3. 일반적인 단어는 하나의 토큰으로, 드문 단어는 서브워드로 나뉨
        4. 작은 모델에 적합 but 초기에 
    
- Device Map
    - 모델 파라미터를 다양한 하드웨어에 분산 시키는 방식
        `device_map = {"transformer.layer.0": "cuda:0", "transformer.layer.1": "cuda:1"}`

- RoRA(Low-Rank-Rank Adaption)
    일부 레이어를 동결시켜 기존의 정보를 가지고 있으면서, 새로운 정보를 추가적으로 훈련시킬 수 있다.

### 실습 모델 카드

01. MusicGen : https://huggingface.co/facebook/musicgen-small
02. FLAN-T5 : https://huggingface.co/google/flan-t5-xl
03. LLaMA3 : https://huggingface.co/meta-llama/Meta-Llama-3-8B-Instruct