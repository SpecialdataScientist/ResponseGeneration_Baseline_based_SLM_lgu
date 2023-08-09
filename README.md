# code_repository
: 전처리, 검색, 응답 생성 관련 코드 저장

## 1. prprocessing_part
>> (1) **preprocess_code**: LGU에서 인수받은 raw data의 전처리를 수행하는 code로서 train, dev set의 dialogue data가 생성되고, 해당 dialogue data를 기반으로 passage data 생성

## 2. Retrieval_part
>> (1) **package**: LGU Data를 이용해 Polyglot 모델을 Fine-tuning 하였으며, 학습되 모델을 이용해 위키백과 모든 문서를 대상으로 데이터를 증강
>> 
>> (2) **Retrieval_with_aumented_data**: 데이터 증강 및 검색 관련 코드 directory
>>> - **Inpainting**: 검색 성능 향상을 위해 Inpainting 방법론을 적용해 데이터 증강
>>> - **Retrieve**: DPR을 이용한 검색 및 re-ranking 관련 코드

## 3. Response_Generation_part
>> (1) **Baseline_based_SLM**: 검색된 top-1 passage를 이용해 응답 생성을 수행하였으며, SLM (BART-base)를 이용한 한국어 Baseline 모델
>>> - **retrieved_lgu_data**: LGU Data 내 검색 결과에 기반한 응답 생성 모델 directory
>>>> - **Response_Generation_Baseline_based_SLM_lgu**: LGU Data 검색 결과 기반 응답 생성 Baseline 모델
>>> - **retrieved_wiki_lgu_data**: wiki + LGU Data 검색 결과에 기반한 응답 생성 모델 directory
>>>> - **Response_Generation_Baseline_based_SLM_wiki_lgu**: wiki + LGU Data 검색 결과 기반 응답 생성 Baseline 모델
>>
>> (2) **CoT_based_SLM**: CoT (Chain-of-Thought)를 이용해 응답 생성을 수행하였으며, SLM (BART-base)를 이용
>>> - **retrieved_lgu_data**: LGU Data 내 검색 결과에 기반한 응답 생성 모델 directory
>>>> - **Reference_Generation_SLM_lgu**: 검색된 passage 내의 reference를 CoT를 위한 reasoning 정보로 간주하여 해당 reference를 생성하기 위한 단계 코드
>>>> - **Response_Generation_CoT_based_SLM_lug**: Reference Generation Step에서 생성된 reference와 검색된 passage를 이용해 사용자 질의에 대한 최종 답변을 생성하는 단계 코드
>> - **retrieved_wiki_lgu_data**: wiki + LGU Data 검색 결과에 기반한 응답 생성 모델 directory
>>>> - **Reference_Generation_SLM_lgu**: 검색된 passage 내의 reference를 CoT를 위한 reasoning 정보로 간주하여 해당 reference를 생성하기 위한 단계 코드
>>>> - **Response_Generation_CoT_based_SLM_lug**: Reference Generation Step에서 생성된 reference와 검색된 passage를 이용해 사용자 질의에 대한 최종 답변을 생성하는 단계 코드
>>
>> (3) **Response_Generation_based_LLM**: LLM (Polyglot-ko)를 이용한 응답 생성 모델 directory
>> > - **Response_Generation_based_LLM**:  LLM (Polyglot-ko)를 이용한 응답 생성 모델 코드
***
