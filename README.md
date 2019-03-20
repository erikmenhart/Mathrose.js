# Mathrose.js
let n, d, sliderA ,sliderC, sliderB, k, radius, red, gre, blu, col1, col2, col3, button;
setup = () => {
	createCanvas(600, 600);
  //first value
	sliderA = createSlider(1, 100, 100);
	sliderA.position(10, 10);

  //second value
	sliderB = createSlider(1, 100, 100);
	sliderB.position(10, 30);

  //size(radius)
	sliderC = createSlider(10, 1000, 1000);
	sliderC.position(10, 50);
  
  //colour
  red = createSlider(0, 255, 5);
  red.position(10, 70);
  gre = createSlider(0, 255, 5);
  gre.position(10, 90);
  blu = createSlider(0, 255, 5);
  blu.position(10, 110);
  
  
  //don't worry about this
  button = createButton('random')
  button.position(10, 150)
}

draw = () => {
	background(0);
	n = sliderA.value();
	d = sliderB.value();
	radius = sliderC.value();
	k = n / d;
  
  col1 = red.value();
  col2 = gre.value();
  col3 = blu.value();

	translate(width / 2, height / 2);
	noFill();
	stroke(col1, col2, col3);

	beginShape();
	for(let i = 0; i < TWO_PI * d; i += 0.01) {
		const r = radius * cos(k * i);
		const x = r * cos(i);
		const y = r * sin(i)
		vertex(x, y);
	}
	endShape(CLOSE);
}
