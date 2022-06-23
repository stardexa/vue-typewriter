# vue-typewrite

## Proje kullanım şekli
#### İlk olarak altdaki kodları projenize ekleyin 
```
export default {
  name: "App",
  data() {
    return {
      i: 0,
    }
  },
  methods: {
    writeClear() {
      this.i = 0 
    },
    typeWriterText(_title, _ref, _speed = 60) {
      if (this.i < _title.length) {
        let output = '';
        output += _title.charAt(this.i);
        this.i = this.i + 1;
        this.$refs[_ref].innerHTML += output
        setTimeout(() => {
          this.typeWriterText(_title, _ref, _speed)
        }, _speed);
      } else {
        this.writeClear()
      }
    },
  }
}

```
daha sonra html kısmında bir element oluşturup ref 'ini belirmeniz gerekmektedir.
aşşağıdaki kullanım şekliyle kullanabilirsiniz.
```
typeWriterText(_title,_ref,_speed)

Örnek : 
<span ref="name"></span>
typeWriterText('İsminizi Giriniz.','name','30')
```

