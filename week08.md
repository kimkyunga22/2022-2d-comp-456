#2D 디지털 합성
## 키라이트와 영상합성

키라이트 
원본에 손상을 가하지 않고 완성하도록 원본, 카피, 프리멀트 노드를 연결한다.
알파를 따는 부분은 디노이즈, 키라이트를 소프트, 하드 키로 나누어 진행한다.
키믹스, 필터이로드, 블러 순으로 노드 연결 
키믹스에서 로토 추가해 마스크에 연결시 더 뚜렷하게 따도록 A 인풋에 있는 부분을 불러온다.
프리멀트는 배경과 합치기 전에 배경의 초록 빼지도록 곱해주는 것이다.
(카피 한 후 원래색으로 돌려준다 = 알파를 날려준다.
소프트 매트도 알파가 0이 될 정도로는 선명해야한다.
키라이트 – 이로드 – 블러  채널머지 통해 소프트와 노드 연결한다.

Ibk 기즈모는 키라이트처럼 키를 빼는 노드이다.
소프트하고 디테일하게 빠져서 인물을 딸때 자주 사용하는 추세임
디퍼런스 노드 – 간단한건 이 노드로도 알파를 추출하는 것이 가능하다.

합성 영상을 완성하는데 도움이 되는 정보들
두개 동시에 보기 위해서는 와이퍼 기능을 사용한다. 단축키로는 w이다.
백드롭 노드는 한번에 묶을 수 있는 노드이다. 
콘스탄트는 면 노드이다. 이 노드를 제일 아래 깔고 시작한다. 
이미지 노드에 바로 리포맷을 머지 오버로 연결해 올리면 사이즈가 맞추어진다.
리포맷에 트랜스폼 노드 연결해 이동하는 것이 가능하다.  
오버 머지에서 Set bbox to 항목을 b로 체크하면 필요없는 부분의 이미지 메모리가 킵 되어 없어져 더 빨라지고 파일이 가벼워진다.
B 인풋을 기준으로 아래로 직선으로 이어지게 정리하는 것이 좋다.
프리퍼런스 – 로컬라이제이션 – 로컬라이즈 투 

그레이드노드 – 색보정보다는 화이트 벨런스 , 세츄레이션, 전체톤 등을 맞출때 많이 사용한다.
리버스 체크시 보정한 색상의 반대 톤으로 바뀐다.
그림자는 리프트, 중간톤은 감마, 밝은톤은 게인이다. 멀티플라이도 게인과 비슷한 역할을하며, 필요시 섞어서 사용한다.
보통 톤을 조정할 경우 블랙포인트, 화이트 포인트 맞추고, 리프트 조정하고, 게인, 감마의 순으로 진행한다.
오프셋은 값이 전체적으로 다 변화가 되는 것이다.
감마는 중간톤을 부스트하거나 감소시킨다. 리니어가 아닌 곡선으로 들어가서 되돌리기 어렵다는 특징이있다.
여러개의 영상을 합성할때 톤이 따로 놀면 안되기때문에 톤을 조정해 맞추어준다. 
그레이드에서 톤 맞춰준다. 컬러휠에서 레드채널, 그린채널, 블루채널 세가지를 각각 채널별로 바꿔보며 맞춘다. 
보통 톤 조정 순서 – 블랙포인트, 화이트 포인트, 리프트, 게인, 감마 
컬러코렉트 노드는 그레이드와 비슷하지만, 채도조절 기능이 있다.
하지만, 세츄레이션 노드도 아예 따로 존재한다.

컷별로 합성 후 프리미어 등으로 편집해 총 결과물 영상 합쳐도 된다.

리포맷에서 픽셀 종류를 정할 수 있다.
노드 컨카테네이션을 지켜야한다. 똑같은 노드끼리 일관있게 정리해야 원본을 더욱 보존하는 것이 가능해진다.
어펜드 클립 노드는 노드와 노드를 연결해주는 노드 프리미어같은 컷편집 역할을 한다.

렌더링 
Write 노드로 렌더링한다. 파일 경로 설정한다. 이때 확장자 꼭 붙여줘야함 .mov 
보통 일반적인 작업의경우 SRGB 로 설정 H264로 렌더링을 많이 한다.