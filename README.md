# form_practice.js

class FormValidation {
  
  static formSubmit (){
    let form = document.getElementById("form_sample");
    form.addEventListener("submit", function(event){
      event.preventDefault();
      let name = document.getElementById("name").value;
      let gender = document.getElementsByName("Gender");
      let subject = document.getElementsByName("subject");
                    
      let selectedGender ="";
      let selectedSubject = "";
      Array.from(gender).forEach((sex)=>{
        if(sex.checked){
          selectedGender+= sex.value;
        }
      });
      Array.from(subject).forEach((subject)=>{
          if(subject.checked){
            selectedSubject+= subject.value +", ";
          }
      });
      let email = document.getElementById("email").value;
      let phone = document.getElementById("phone").value;
      let city = document.getElementById("city").value;
      let address = document.getElementById("address").value;

      console.log(email, phone, city, address);
      console.log(selectedSubject);
                

      let w = open("", "_blank", "width=500px,height=400px");
      w.document.write(`<h4>Name: ${name}</h4>`);
      w.document.write(`<p>Gender: ${selectedGender}</p>`);
      w.document.write(`<p>Subject: ${selectedSubject}</p>`);
      w.document.write(`<p>Email: ${email}</p>`);
      w.document.write(`<p>Phone: ${phone}</p>`);
      w.document.write(`<p>City: ${city}</p>`);
      w.document.write(`<p>Address: ${address}`);    
      w.document.write(`<button onclick="self.close()">Click</button>`);
      w.document.write(`<button onclick="print()">Print</button>`);
    });

  }
  static nameValidation () {
      let name = document.getElementById("name").value
      let namePattern = /^[a-zA-Z]{4,20}$/
      let nameInput = document.getElementById("name")
      let namevalidation = document.getElementById("namevalidation")
    if(namePattern.test(name)){
      nameInput.style.border="3px solid green"
      namevalidation.style.display = "none"
    }else{
      nameInput.style.border="3px solid hotpink"
      namevalidation.style.display = "block"
    }
  }
  static emailValidation () {
    let email = document.getElementById("email").value;
    let emailPattern = /^[a-zA-Z0-9]{3,}[@][a-z]{3,}[.][a-z]{2,}$/;
    let emailInput = document.getElementById("email")
    let emailvalidation = document.getElementById("emailvalidation")
    if (emailPattern.test(email)) {
      emailInput.style.border = "3px solid green"
      emailvalidation.style.display = "none"
    } else {
      emailInput.style.border = "3px solid hotpink"
      emailvalidation.style.display = "block"
    }
   
  }
  
}
