# AngularCalculation

# Web Page for Mathematical Calculations using Angular

## AIM:
To design a dynamic website to perform mathematical calculations using Angular Framwork

## DESIGN STEPS:

### Step 1:

Requirement collection.

### Step 2:

Creating the layout using HTML and CSS in component.html file

### Step 3:

Write typescript to perform the calculations.

### Step 4:

Validate the layout in various browsers.

### Step 5:

Validate the HTML code.

### Step 6:

Publish the website in the given URL.

## PROGRAM :
## cyclinder-component.html:
```
<style>
    h2{
background-color: rgb(120, 151, 151);
color: rgb(100, 67, 94);
}
.container {
  display: block;
  background-color: #95a197;
  min-height: 200px;
  margin-top: 100px;
}
.al{
    text-align: center;
    font-size: 25px;
}

</style>
<div class="container">
<div class="al">
    <h2>VOLUME OF CYLINDER</h2>
    Radius=<input type="text"[(ngModel)]='radius'>Meters<br/>
    Height=<input type="text"[(ngModel)]='height'>Meters<br/>
    <input tAype="button" (click)="onCalculate()" value="CalculateArea"><br/>
    Volume=<input type="text" [value]="volume"> Meters<sup>3</sup><br/>
    volume=π*r^2*h

</div>
</div>
```
## cylinder-component.ts:
```
import { Component } from "@angular/core";

@Component({
    selector:'Cylinder-Vol',
    templateUrl:'./cylinder.component.html'
})
export class CylinderComponent{
    radius:number;
    height:number;
    volume:number;
    constructor(){
        this.radius=0;
        this.height=0;
        this.volume=0;
    }
    onCalculate(){
        this.volume = 22/7*this.radius**2*this.height
    }
}
```
## rectangle-component.html:
```
<style>
    h2{
background-color: rgb(56, 92, 92);
color: rgb(77, 181, 241);
}
.container {
  display: block;
  background-color: #e0e9e0;
  min-height: 200px;
  margin-top: 100px;
}
.al{
    text-align: center;
    font-size: 25px;
}

</style>

<div class="container">
    <div class="al">
    <h2>AREA OF RECTANGLE</h2>
    Length=<input type="text"[(ngModel)]='length'>Meters<br/>
    Breadt=<input type="text"[(ngModel)]='breadth'>Meters<br/>
    <input type="button" (click)="onCalculate()" value="CalculateArea"><br/>
    Area=<input type="text" [value]="area"> Meters<sup>2</sup><br/>
</div>

</div>
```
## rectangle-component.ts:
```
import { Component } from "@angular/core";

@Component({
    selector:'Rectangle-Area',
    templateUrl:'./rectangle.component.html'
})
export class RectangleComponent{
    length:number;
    breadth:number;
    area:number;
    constructor(){
        this.length=0;
        this.breadth=0;
        this.area=0;


    }
    onCalculate()
    {
            this.area = this.length*this.breadth
    }
}
```
## app.component.css:
```
h2{
  text-align: center;
  color: rgb(232, 231, 243);
  margin-top: 10px;


}
.container {
  width: 800px;
  margin-left: auto;
  margin-right: auto;
}
.backgd{
  background-color: rgb(202, 194, 194) ;
}
.footer{
    text-align: center;
    font-size: 30px;
    color: rgb(164, 174, 194);
    background-color: rgb(13, 13, 14);
    margin-top: 10px;
}
```
## app.component.html:
```
<div class="backgd">
  <h2>MATH CALCULATION</h2>
  <div class="container">
      
<Rectangle-Area>

</Rectangle-Area>

<Cylinder-Vol>

</Cylinder-Vol>


<div class="footer">DEVELOPED BY: Prethiveerajan P</div>

  </div>

</div>
```
##  app.component.spec.html:
```
import { TestBed } from '@angular/core/testing';
import { AppComponent } from './app.component';

describe('AppComponent', () => {
  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [
        AppComponent
      ],
    }).compileComponents();
  });

  it('should create the app', () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app).toBeTruthy();
  });

  it(`should have as title 'mathcalculation'`, () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app.title).toEqual('mathcalculation');
  });

  it('should render title', () => {
    const fixture = TestBed.createComponent(AppComponent);
    fixture.detectChanges();
    const compiled = fixture.nativeElement as HTMLElement;
    expect(compiled.querySelector('.content span')?.textContent).toContain('mathcalculation app is running!');
  });
});
```
## app.component.ts:
```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'mathcalculation';
}
```
## app.module.ts:
```
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { BrowserModule } from '@angular/platform-browser';

import { AppComponent } from './app.component';
import { CylinderComponent } from './cylinder/cylinder.component';
import { RectangleComponent } from './rectangle/rectangle.component';

@NgModule({
  declarations: [
    AppComponent,RectangleComponent,CylinderComponent,
  ],
  imports: [
    BrowserModule,FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## OUTPUT:
![OUTPUT](pd.png)


## Result:
Thus  we sucessfully design a dynamic website to perform mathematical calculations using Angular Framwork
