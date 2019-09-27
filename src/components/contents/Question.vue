<template>
	<v-simple-table class="mx-auto">
		<template v-slot:default>
			<thead>
				<tr>
					<th class="text-left">제목</th>
					<th class="text-left">질문자</th>
					<th class="text-left">작성일</th>
					<th class="text-left">조회수</th>
					<th class="text-left">추천</th>
					<th class="text-left">답글</th>
				</tr>
			</thead>
			<tbody>
				<tr v-for="item in desserts" :key="item.name">
					<td>{{ item.title }}</td>
					<td>{{ item.writer }}</td>
					<td>{{ item.date }}</td>
					<td>{{ item.views }}</td>
					<td>{{ item.likes }}</td>
					<td>{{ item.replies }}</td>
				</tr>
			</tbody>
		</template>
	</v-simple-table>
</template>

<script>
	export default {
		data() {
			return {
				desserts: [{
						title: '어케하나요?',
						writer: "정현민",
						date: "방금전",
						views: "1",
						replies: "0",
						likes: "2",
					},
					{
						title: 'questions?',
						writer: "해군",
						date: "1분전",
						views: "12",
						replies: "0",
						likes: "3",
					},
					{
						title: '질문 드립니다.?',
						writer: "국방부",
						date: "3분전",
						views: "53",
						replies: "1",
						likes: "4",
					},
					{
						title: '답변 부탁드리겠습니다.',
						writer: "익명",
						date: "5분전",
						views: "120",
						replies: "1",
						likes: "12",
					},
					{
						title: '질문 제발 빨리',
						writer: "닉네임",
						date: "21분 전",
						views: "123",
						replies: "1",
						likes: "42",
					},
					{
						title: '이렇게 될 경우에는?',
						writer: "병무청",
						date: "1시간 전",
						views: "233",
						replies: "1",
						likes: "52",
					},
					{
						title: '급한 질문 드립니다.',
						writer: "육군",
						date: "1일 전",
						views: "423",
						replies: "4",
						likes: "12",
					},
				],
			}
		},
	}
</script>