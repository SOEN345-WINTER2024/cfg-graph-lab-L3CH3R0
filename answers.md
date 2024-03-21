## Lab 7 :
#Part 1 - Basic Calculator : 
1) Draw the CFG graph for onClick()<img width="1161" alt="Screenshot 2024-03-08 at 3 58 59 PM" src="https://github.com/SOEN345-WINTER2024/cfg-graph-lab-eo2000/assets/116772744/b6b0dc30-4eff-4f4a-afd2-de99e48ed5c2">

2)  Compute node coverage for this CFG
- TR : [1][2][3][4][5][6][7][8][9][10][11][12][13][14][15][16][17][18][19][20][21][22]
- Test paths : [1,2,22][1,3,22][1,4,22][1,5,22][1,6,22][1,7,22][1,8,22][1,9,22][1,10,22][1,11,22][1,12,22][1,13,22][1,14,22][1,15,22][1,16,22][1,17,18,22][1,17,19,22][1,17,20,22][1,17,21,22]

3) Compute edge coverage for this CFG
- TR : [1,2][1,3][1,4][1,5][1,6][1,7][1,8][1,9][1,10][1,11][1,12][1,13][1,14][1,15][1,16][1,17][17,18][17,19][17,20][17,21][18,22][19,22][20,22][21,22]
[2,22][3,22][4,22][5,22][6,22][7,22][8,22][9,22][10,22][11,22][12,22][13,22][14,22][15,22][16,22]
- Test paths : [1,2,22][1,3,22][1,4,22][1,5,22][1,6,22][1,7,22][1,8,22][1,9,22][1,10,22][1,11,22][1,12,22][1,13,22][1,14,22][1,15,22][1,16,22][1,17,18,22][1,17,19,22][1,17,20,22][1,17,21,22]

4) Compute edge-pair coverage for this CFG
- TR : [1,2,22],[1,2,22],[1,3,22],[1,4,22],[1,5,22],[1,6,22],[1,7,22],[1,8,22],[1,9,22],[1,10,22],[1,11,22],,[1,12,22],[1,13,22],[1,14,22],[1,15,22],[1,16,22],[1,17,18],[1,17,19], [1,17,20],[1,17,21],[17,18,22],[17,19,22],[17,2022],[17,21,22]
- Test paths : [1,2,22][1,3,22][1,4,22][1,5,22][1,6,22][1,7,22][1,8,22][1,9,22][1,10,22][1,11,22][1,12,22][1,13,22][1,14,22][1,15,22][1,16,22][1,17,18,22][1,17,19,22][1,17,20,22][1,17,21,22]

5) Draw the EFG graph for the Calculator App
   ![IMG_3417](https://github.com/SOEN345-WINTER2024/cfg-graph-lab-eo2000/assets/116772744/c312c31e-5de3-4ad0-9897-2920376c0760)


#Part 2 - Project App :
```Kotlin
    override fun onPostCreate(savedInstanceState: Bundle?) {
        super.onPostCreate(savedInstanceState)
        if (!Camera.doesDeviceHaveFlash(packageManager)) return
        initButtonClickListeners()
        checkDeviceSupport()
        if (!Safe.getBoolean(Safe.FLASH_ACTIVE, false) && !intentFlash) {
            executeAppStartFlash()
        }

        vibrateButtons = Safe.getBoolean(Safe.BUTTON_VIBRATION, true)
        vibrateMorse = Safe.getBoolean(Safe.MORSE_VIBRATION, true)
        val systemVibrator = (getSystemService(Context.VIBRATOR_MANAGER_SERVICE) as VibratorManager)
            .defaultVibrator
        Vibrator.initialize(systemVibrator)
        AppReviewManager.initiateReviewDialog(this)
    }
```

1) Draw the CFG graph for onPostCreate()
<img width="553" alt="Screenshot 2024-03-21 at 1 39 41 PM" src="https://github.com/SOEN345-WINTER2024/cfg-graph-lab-L3CH3R0/assets/91989855/a3b32bf8-2b90-4ab8-af9e-5f0bf0613b2e">

2) Compute node coverage for this CFG:
   TR: [1],[2],[3],[4],[5],[6],[7],[8],[9],[10]
   Test Path: [1,2,3,5],[1,2,3,4],[1,2,6,7,8],[1,2,6,9,10]
4) Compute edge coverage for this CFG
   TR:[1,2],[2,3],[3,5],[3,4],[2,6],[6,7],[7,8],[6,9],[9,10]
   Test Path:[1,2,3,5],[1,2,3,4],[1,2,6,7,8],[1,2,6,9,10]
5) Compute edge-pair coverage for this CFG
   TR: [1,2,3],[2,3,5],[2,3,4],[1,2,6],[6,7,8],[6,9,1]
   Test Path:
6) Draw the EFG graph for this method
![Screen Shot 2024-03-15 at 4 25 24 PM](https://github.com/SOEN345-WINTER2024/cfg-graph-lab-L3CH3R0/assets/91989855/c40e43d5-6346-44ad-afb2-30154f1e561e)
