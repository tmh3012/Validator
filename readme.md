# Library Validator with js 
## Javascript Basic Course - F8-Fullstack 

### Config
```
document.addEventListener('DOMContentLoaded', function(){
Validator({
        form: '#form-1', // form selector
        formGroupSelector: '.form-group', // input element group selector
        errorSelector: '.form-message', // input element of display error message
        rules: [
          Validator.isEmail('#email'),
          Validator.isRequired('#email'),
          Validator.minLength('#password', 6),
          Validator.isConfirmed('#password_confirmation', function () {
            return document.querySelector('#form-1 #password').value;
          }, 'Mật khẩu nhập lại không chính xác')
        ],
        onSubmit: function (data) {
          // Call API submit form
        }
      });
});
```
#### Available rules
1. Validator.isRequired('selector', 'message');
2. Validator.isEmail('selector', 'message');
3. Validator.isMinlength('selector','length of password', 'message');
4. Validator.isConfirmed('selector',getConfirmValue, 'message');