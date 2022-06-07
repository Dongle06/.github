# 동글 (Team 조나단)
동글 URL : https://dongle-books.web.app/

사용설명서 : https://github.com/Dongle06/.github/blob/main/ReleaseNote.md


## Introduction
아이들의 창의력 증진과 집중력 및 활동성 향상을 위한 모션, 표정, 음성 인식 기반 참여형 웹 동화 서비스

<br/>

## UI
![](https://velog.velcdn.com/images/yeah7598/post/2ba6a0a7-2c4f-4e1e-b082-bf931e23004f/image.png)
![](https://velog.velcdn.com/images/yeah7598/post/9349c29f-ac4b-4b82-870b-18466186b69d/image.png)
주요 장면 영상: https://drive.google.com/file/d/1vA_0iu8mc7oFnzggOMLFLDHkaWK4ORjZ/view?usp=sharing

포스터 및 시연 영상: https://youtu.be/R2qC4EqBpCc

<br/>

## System Architecture
<img width="583" alt="image" src="https://user-images.githubusercontent.com/87087459/170506031-0cae80ff-b072-46ce-89a1-acef4261b4c0.png">
프론트는 리액트 라이브러리를 사용하고, 백엔드의 경우 Django를 이용하여 api 서버를 구축하였습니다. 모션인식의 경우 poseNet으로 유저의 자세를 실시간으로 인식하도록 하였습니다. 표정인식은 텐서플로우를 사용해 표정을 학습하고, tensorflow.js로 변환하여 실시간 인식을 하고 있습니다. 음성인식의 경우  web speech api 중 리액트 라이브러리인 react-speech-kit를 사용하여 음성을 인식하고 인식 결과 데이터를 처리하였습니다. 배포는 aws 클라우드 서버를 이용해 진행하였으며, docker와 github actions으로 ci/cd를 적용하였습니다.

<br/>

## System flow
<img width="595" alt="image" src="https://user-images.githubusercontent.com/87087459/170506270-a28ff7ee-0a10-468a-97f5-9d697f748bbb.png">
로그인을 마친 사용자는 원하는 책을 선택하여 서비스를 시작합니다. 애니메이션이 진행되는 도중 등장하는 미션에서 웹캠을 통해 유저의 모습을 실시간 input으로 받으면, 표정인식과 모션인식에서 각각 모델을 거쳐 결과를 반환하게 됩니다. 
음성인식의 경우 마이크를 통해 유저의 음성을 받아, 이를 인식하여 결과를 반환합니다.
반환된 결과를 바탕으로 동화가 진행되고 중간 종료 시, 데이터베이스에 종료 시 페이지 정보를 저장합니다.

<br/>

## Contributor

|맹수연|김윤지|안예린|이진경|
|---|---|---|---|
|Backend|AI/DevOps|Frontend|AI|

<br/>

## Poster
![Dongle](https://user-images.githubusercontent.com/70802352/170505471-bd22a64a-8fb9-4d99-9e58-88d80ea8a548.jpg)

