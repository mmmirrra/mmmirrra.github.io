---
layout: post
title:  "University Mathematics: Graph Equations"
date:   2024-03-25 09:00:00 +0900
categories: [University Mathematics]
---

### equation   
// 방정식   
   
// 직교좌표 체계에서 그래프로 표현   
- Graphical representation in orthogonal coordinate systems   
   
### orthogonal coordinate   
// 직교좌표   
   
// 수직선(y축)과 수평선(x축)을 좌표축 → 두 개 실수 표현   
- The vertical line (y-axis) and the horizontal line (x-axis) are coordinate axes → represent two real numbers   
   
### the distance between two points   
// 두 점 간의 거리   
   
- d = √ ((x<sub>2</sub> - x<sub>1</sub>)² + (y<sub>2</sub> - y<sub>1</sub>)²)   
- Pythagorean theorem   
  - c² = a² + b²   
  - c = √ (a² + b²)   
   
### the representation of an equation   
// 방정식의 표현   
   
// 방정식 : x, y 값에 따라 참, 거짓이 달라지는 등식 → 직교좌표에 표현 가능   
- Equation : True and False vary depending on x and y values → Expressable in orthogonal coordinates   
   
// 예시 : y = 2x + 1   
// (1, 3)은 2 + 1 = 3 이 되므로 등식 만족   
// (2, 1)은 4 + 1 = 5 가 되므로 등식을 만족하지 않음   
- Example : y = 2x + 1   
  - Equation is satisfied because (1, 3) is 2 + 1 = 3   
  - Equation is not satisfied because (2, 1) is 4 + 1 = 5   
   
// 예시 : 두 점 (3, 2)와 (4, 3)을 지나는 직선   
- Example : A straight line passing through two points (3, 2) and (4, 3)   
  - slope =  <sup>change in y</sup>/<sub>change in x</sub> = <sup>3 - 2</sup>/<sub>4 - 3</sub> = 1   
  - equation : y - 2 = x - 3 → y = x - 1   
   
// 방정식 : 임의의 두 점 (x<sub>1</sub>, y<sub>1</sub>)과 (x<sub>2</sub>, y<sub>2</sub>)를 지나는 직선 표현   
// 기울기 : x값의 변화에 대한 y값의 변화의 비   
// - 기울기 β = <sup>y<sub>2</sub> - y<sub>1</sub></sup>/<sub>x<sub>2</sub> - x<sub>1</sub></sub>   
// 절편 : 직선이 y축과 만나는 점   
// - y = βx + b → x = 0일 때의 b의 값을 절편이라고 함   
- equation : A straight line representation through any two points (x<sub>1</sub>, y<sub>1</sub>) and (x<sub>2</sub>, y<sub>2</sub>)   
- slope : The ratio of the change in y value to the change in x value   
  - slope β = <sup>y<sub>2</sub> - y<sub>1</sub></sup>/<sub>x<sub>2</sub> - x<sub>1</sub></sub>   
- intercept: The point where the straight line meets the y-axis   
  - y = βx + b → When x = 0, the value of b is called the intercept   
   
// 예시 : (2, 1)과 (4, 5)를 지나는 직선의 방정식을 구하시오   
- Example : Find an equation of the straight line passing through (2, 1) and (4, 5)   
  - slope β = <sup>5 - 1</sup>/<sub>4 - 2</sub> = <sup>4</sup>/<sub>2</sub> = 2   
  - y = 2x + b   
  - 1 = 2·2 + b   
  - b = -3   
  - ∴ y = 2x - 3   
   
// 예시 : y = x² + 1 의 그래프를 그리시오   
- Example : Draw a graph of y = x² + 1   
   
|x|-2|-1|0|1|2|
|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>y</b>|5|2|1|2|5|
   
### circle   
// 원   
   
// 한 점으로부터 일정한 거리에 있는 점들의 모임   
- A collection of points at a certain distance from a point   
  - √ ((x - x<sub>1</sub>)² + (y - y<sub>1</sub>)²) = r   
  - (x - x<sub>1</sub>)² + (y - y<sub>1</sub>)² = r²   
   
// 예시 : 중심이 (1, 2)이고 반지름이 5인 원을 그리시오   
- Example : Draw a circle with center (1, 2) and radius 5   
  - (x - 1)² + (y - 2)² = 5²   
   
|x|1 ± √21|0|
|:---:|:---:|:---:|
|<b>y</b>|0|2 ± √24|
   
### ellipse   
// 타원   
   
// 두 고정점에 이르는 거리의 합이 일정한 점들의 집합   
- a set of points where the sum of the distances to two fixed points is constant   
   
- two fixed points : A(-c, 0), B(c, 0)   
- a point away from two fixed points : C(x, y)   
  - √ ((x + c)² + y²) + √ ((x - c)² + y²) = 2a   
  - ∴ <sup>x²</sup>/<sub>a²</sub> + <sup>y²</sup>/<sub>b²</sub> = 1   
  - b² = a² - c²   
  - ∴ It's an ellipse   
   
- if a = b   
  - <sup>x²</sup>/<sub>a²</sub> + <sup>y²</sup>/<sub>a²</sub> = 1   
  - x² + y² = a²   
  - ∴ It's a circle   
   
// 예시 : 초점이 A(-1, 0), B(1, 0)이고, A, B를 잇는 거리의 합이 4인 타원을 구하시오   
- Example : Find an ellipse with focal points A(-1, 0), B(1, 0), and the sum of the distances connecting A and B is 4   
  - √ ((x + 1)² + y²) + √ ((x - 1)² + y²) = 4 = 2a   
  - a = 2, c = 1   
  - b² =  a² - c² = 4 - 1 = 3   
  - <sup>x²</sup>/<sub>a²</sub> + <sup>y²</sup>/<sub>b²</sub> = <sup>x²</sup>/<sub>4</sub> + <sup>y²</sup>/<sub>3</sub> = 1   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
