# reinforcement
Question 1 (6 points): Value Iteration
Thay đổi value theo số lần lăp, mỗi lần lặp:

+ Xét các state khả dụng, chỉnh sửa lại các value tương ứng với từng state gán bằng max(computeQValueFromValues(state, a)) với các action khả dụng
+ Hàm computeQValueFromValues(state, a): đưa ra Q(s,a): giá trị sau khi thực hiện action a

Question 2 (1 point): Bridge Crossing Analysis
Thay đổi giá trị discount và noise

Question 3 (5 points): Policies
livingReward: điểm thưởng khi sống sót
1, Đi đường dưới, đến vị trí +1: livingReward âm
2, Đi đường trên, đến vị trí +1: livingReward = 0,noise > 0=> khi đó sẽ phải tránh vực
3, Đi đường dưới, đến vị trí +10:livingReward > câu 1 nhưng < 0, phù hợp để ưu tiên đến vị trí +10 (-0.5) 
4, Đi đường trên, đến vị trí +10:livingReward > câu c nhưng < (-0.1) 
5, Sống càng lâu càng tốt: livingReward rất cao (+100)

Question 4 (5 points): Q-Learning
Cài đặt hàmhàm Q-learning:
V*(s): hàm getValue(state) = maxQ(s,a), a = hàm computeValueFromQValues(state)
Việc cập nhật các values được cài đặt ở hàm update

Question 5 (3 points): Epsilon Greedy
+ Có tỉ lệ thực hiện hành động khám phá
+ Cài đặt hàm getAction

lấy ramdom.random()(0->1)
+ Với tỉ lệ nhỏ hơn tỉ lệ khám phá (flipcoin(p) return True): thực hiện hành động khám phá, các hành động là ngẫu nhiên
+ Nếu không thực hiện theo chính sách ban đầu

Question 6 (1 point): Bridge Crossing Revisited
Q-learning với bài toán qua cầu Q2: Do số lần lặp nhỏ (k = 50):
 + Với e lớn thì phần lớn xuống vực
 + Với e nhỏ thì phần lớn trở về điểm ban đầu 
