> 원본: [FinanceData/OpenDartReader](https://github.com/FinanceData/OpenDartReader)의 포크

# 포크 변경점

1. `dart.OpenDartReader`의 클래스가 모듈 이름인 `OpenDartReader`와 겹쳐서, IDE가 resolve하기 어려워하는 상황이 발견됨.
조치로 `sys.modules['OpenDartReader']` 를 `sys.modules['dart']`로 바꿈
2. `pyproject.toml` 추가, `uv`로 구동 가능하게끔 만듦
3. 
설치 방법:

1. `pyproject.toml`의 `dependencies` 배열에 추가
    ```toml
   dependencies = [
      "dart-fork @ git+https://github.com/TTPICKTTTERA/dart-fork.git@master",
   ]
   ```
   
2. 명령어 실행:
    ```shell
    uv sync && uv pip install -e .
    ```