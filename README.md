<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1e96acaa-8b69-4639-a5b1-4fa3611de358" />

### What is ng-container?
- <ng-container> is a logical container in Angular that does not render any extra HTML in the DOM. It’s used to group structural directives like *ngIf, *ngFor,
   or *ngSwitchCase without adding extra elements like  ``` <div> or <span>.```


## Ng Container in angular
------------------------------------------------

1. Without Using ng-container  and using by ngSwitch
-------------------------------------------------------
## Step1: status.component.ts
```
import { CommonModule } from '@angular/common';
import { Component } from '@angular/core';

@Component({
  selector: 'app-status',
  imports: [CommonModule],
  templateUrl: './status.component.html',
  styleUrl: './status.component.css'
})
export class StatusComponent {
 status:string='pending';
 setStatus(newStatus:string):void{
  this.status=newStatus;

 }
}
## Step2: status.component.html
<p>status works!</p>
<hr/>
<div class="container mt-5">
    <h2>Status Work With and Without &lt; ng-container &gt;</h2>
    <!--Button to change the status-->
    <button class="btn btn-warning me-2" (click)="setStatus('pending')">
        Pending
    </button>   
    <button class="btn btn-warning me-2" (click)="setStatus('approved')">
         Approved
    </button>
    <button class="btn btn-warning me-2" (click)="setStatus('rejected')">
         Rejected
    </button>
</div>
<!--Without ng-container -->
<div [ngSwitch]="status" class="border p-3">
    <ng-container *ngSwitchCase="'pending'">
        <p class="text-warning">Your Request is Pending...</p>
    </ng-container>
    <ng-container *ngSwitchCase="'approved'">
        <p class="text-warning">Your Request is Approved...</p>
    </ng-container>
    <ng-container *ngSwitchCase="'rejected'">
        <p class="text-warning">Your Request is Rejected...</p>
    </ng-container>
    <ng-container *ngSwitchDefault>
        <p class="text-warning">Unknown ..</p>
    </ng-container>
</div>



<hr/>

```
2. With Using ng-container
```

<hr/>
<h2>With ng-container</h2>
<div [ngSwitch]="status" class="border p-3">
  <ng-container *ngSwitchCase="'pending'">
     <p class="text-warning">Your Request is Pending...</p>
  </ng-container>
  <ng-container *ngSwitchCase="'approved'">
     <p class="text-success">Your Request is Approved...</p>
  </ng-container>
  <ng-container *ngSwitchCase="'rejected'">
     <p class="text-danger">Your Request is Pending...</p>
  </ng-container>
  
</div>


<hr/>
```

