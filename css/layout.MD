위아래 중간 센터, 양옆 센터
====
```
          <ion-row>
            <ion-col [ngClass]="userMeasNeuro ? 'measArc' : 'NEURO_EMPTY' | translate" style="display: grid;">
              <div style="margin:auto" *ngIf="userMeasNeuro" [routerLink]="['/meas-neuro', userMeasNeuro.reg_dt]">
                <p style="text-align: center; margin: 2px">
                  <ion-text color="light" style="margin:auto; font-size: 3.5vw;">{{'EEG_HISTORY_TEXT_03' | translate}}</ion-text>
                </p>
                <p style="text-align: center; margin: 2px">
                  <ion-text color="light" style="font-size: 8vw;">{{userMeasNeuro.tot}}</ion-text>
                  <ion-text color="light" style="font-size: 4vw;">{{'EEG_HISTORY_TEXT_02' | translate}}</ion-text>
                </p>
              </div>
            </ion-col>
            <ion-col [ngClass]="userMeasPulse ? 'measArc' :  'PULSE_EMPTY' | translate " style="display: grid;">
              <div style="margin:auto" *ngIf="userMeasPulse" [routerLink]="['/meas-pulse', userMeasPulse.reg_dt]">
                <p style="text-align: center; margin: 2px">
                  <ion-text color="light" style="margin:auto; font-size: 3.5vw;">{{'HRV_HISTORY_TEXT_03' | translate}}</ion-text>
                </p>
                <p style="text-align: center; margin: 2px">
                  <ion-text color="light" style="font-size: 8vw;">{{userMeasPulse.ans_age}}</ion-text>
                  <ion-text color="light" style="font-size: 4vw;">{{'HRV_HISTORY_TEXT_02' | translate}}</ion-text>
                </p>
              </div>
            </ion-col>

          </ion-row>
```