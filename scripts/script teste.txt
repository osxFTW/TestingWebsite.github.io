let angryKid = document.querySelector('img');

angryKid.onclick = function() {
	let mySrc = angryKid.getAttribute('src');
	if(mySrc == 'images/bg-sus.png'){
		angryKid.setAttribute('src','images/bg-change.jpg')
	}else {
		angryKid.setAttribute('src','images/bg-sus.png');
	}
}

let changeButton = document.querySelector('button');
let myHeading = document.querySelector('h1');
let myPassShow = document.querySelector('h3');
let passButton = document.querySelector('h4');

function setUserName() {
	let myName = prompt('Please enter your name.');
	if (!myName) {
		setUserName();
	} else {
		localStorage.setItem('name', myName);
		myHeading.textContent = 'Bine ați venit în comunitatea noastră, ' + myName;
	}
}

if (!localStorage.getItem('name')) {
	setUserName();
} else {
	let storedName = localStorage.getItem('name');
	myHeading.textContent = 'Bine ați venit în comunitatea noastră, ' + storedName;
}

changeButton.onclick = function () {
	setUserName();
}

function setPassword() {
	let myPass = prompt('Please enter your password.')
	if (!myPass) {
		setPassword();
	} else {
		localStorage.setItem('pass', myPass);
    }
}

let passStored = localStorage.getItem('pass');

passButton.onclick = function () {
	setPassword();
}


if (!localStorage.getItem('pass')) {
	setPassword();
}

myPassShow.onclick = function () {
	myPassShow.textContent = passStored;
}



