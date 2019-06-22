# Полезные миксины для верстки с SASS
## Перевод из px в rem
##### SASS
```sass
.block
  +fz(16)
```
##### CSS на выходе
```css
.block
  font-size: 1 rem
```
## Медиа запросы
##### SASS
```sass
.block
  font-size: 16px
  +mq(md)
    font-size: 14px
```
##### CSS на выходе
```css
.block{
  font-size: 16px;
}
  
@media screen and (max-width: 992px) {
  .block {
    font-size: 14px; 
   } 
}
```
## Центрирование абсолютным позиционированием
##### SASS
```sass
.block
  +center(both) 
// both/vertical/horizontal
```
##### CSS на выходе
```css
.block {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%); 
}
```
## Редактирование плейсхолдера
##### SASS
```sass
input
  +placeholder
    color: #cecece
```
##### CSS на выходе
```css
input.placeholder {
  color: #cecece;
}
input:-moz-placeholder {
  color: #cecece;
}
input::-moz-placeholder {
  color: #cecece;
}
input:-ms-input-placeholder {
  color: #cecece;
}
input::-webkit-input-placeholder {
  color: #cecece;
}
```
## Пропорциональное уменьшения блока
При изменении размера родительского блока, блок будет сохраняя свои пропорции
##### SASS
```sass
iframe
  +ratio(16,9)
```
##### CSS на выходе
```css
iframe {
  position: relative;
  overflow: hidden;
  padding-top: 56.25%; 
}
iframe > iframe {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border: 0; 
}
```
