# FDC2114


#include "FDC2112.h"

FDC2112_Init(&hi2c3, FDC2214_I2C_ADDR_1, &fdc2114);
  //FDC2112_Eneble_Convertion(&fdc2114);
  //FDC2112_Set_Configuration(&fdc2114);


  //FDC2112_Set_Reg();
  HAL_Delay(100);
  FDC2112_Set_Reg (&fdc2114,FDC2214_RESET_DEV,0x8000); // RESET_DEVICE
  HAL_Delay(100);

  FDC2112_Get_Reg (&fdc2114,FDC2214_DEVICE_ID);//read DEVICE_ID
  FDC2112_Get_Reg (&fdc2114,FDC2214_MANUFACTURER_ID);//read MANUFACTURER_ID
  FDC2112_Get_Reg (&fdc2114,FDC2214_STATUS);//read STATUS
  FDC2112_Get_Reg (&fdc2114,FDC2214_ERROR_CONFIG);//read ERROR_CONFIG

  //? 0x00FF
  FDC2112_Set_Reg (&fdc2114,FDC2214_RCOUNT_CH0,0x0100);//0x0000-0x00FF: Reserved   0x0100-0xFFFF: Conversion Time (tC) =  (CH_RCOUNTˣ16)/fREF
  FDC2112_Set_Reg (&fdc2114,FDC2214_RCOUNT_CH1,0x0100);//0x0000-0x00FF: Reserved   0x0100-0xFFFF: Conversion Time (tC) =  (CH_RCOUNTˣ16)/fREF
  FDC2112_Set_Reg (&fdc2114,FDC2214_RCOUNT_CH2,0x0100);//0x0000-0x00FF: Reserved   0x0100-0xFFFF: Conversion Time (tC) =  (CH_RCOUNTˣ16)/fREF
  FDC2112_Set_Reg (&fdc2114,FDC2214_RCOUNT_CH3,0x0100);//0x0000-0x00FF: Reserved   0x0100-0xFFFF: Conversion Time (tC) =  (CH_RCOUNTˣ16)/fREF

  FDC2112_Set_Reg (&fdc2114,FDC2214_OFFSET_CH0,0x1000);//Channel Conversion Offset. fOFFSET = (CH_OFFSET/216)*fREF
  FDC2112_Set_Reg (&fdc2114,FDC2214_OFFSET_CH1,0x0000);//Channel Conversion Offset. fOFFSET = (CH_OFFSET/216)*fREF
  FDC2112_Set_Reg (&fdc2114,FDC2214_OFFSET_CH2,0x0000);//Channel Conversion Offset. fOFFSET = (CH_OFFSET/216)*fREF
  FDC2112_Set_Reg (&fdc2114,FDC2214_OFFSET_CH3,0x0000);//Channel Conversion Offset. fOFFSET = (CH_OFFSET/216)*fREF

  FDC2112_Set_Reg (&fdc2114,FDC2214_SETTLECOUNT_CH0,0x0000);//Settle Time  (tS)= (CH_SETTLECOUNTˣ16) ÷ fREF
  FDC2112_Set_Reg (&fdc2114,FDC2214_SETTLECOUNT_CH1,0x0000);//Settle Time  (tS)= (CH_SETTLECOUNTˣ16) ÷ fREF
  FDC2112_Set_Reg (&fdc2114,FDC2214_SETTLECOUNT_CH2,0x0000);//Settle Time  (tS)= (CH_SETTLECOUNTˣ16) ÷ fREF
  FDC2112_Set_Reg (&fdc2114,FDC2214_SETTLECOUNT_CH3,0x0000);//Settle Time  (tS)= (CH_SETTLECOUNTˣ16) ÷ fREF

  FDC2112_Set_Reg (&fdc2114,FDC2214_CLOCK_DIVIDERS_CH0,0x1001);//Table 32. Address 0x14, CLOCK_DIVIDERS_CH0 Field Descriptions
  FDC2112_Set_Reg (&fdc2114,FDC2214_CLOCK_DIVIDERS_CH1,0x1001);//Table 32. Address 0x14, CLOCK_DIVIDERS_CH0 Field Descriptions
  FDC2112_Set_Reg (&fdc2114,FDC2214_CLOCK_DIVIDERS_CH2,0x1001);//Table 32. Address 0x14, CLOCK_DIVIDERS_CH0 Field Descriptions
  FDC2112_Set_Reg (&fdc2114,FDC2214_CLOCK_DIVIDERS_CH3,0x1001);//Table 32. Address 0x14, CLOCK_DIVIDERS_CH0 Field Descriptions

  FDC2112_Set_Reg (&fdc2114,FDC2214_CONFIG,0x1401);//Figure 45. Address 0x1A, CONFIG

  FDC2112_Set_Reg (&fdc2114,FDC2214_MUX_CONFIG,0x000F);//Figure 46. Address 0x1B, MUX_CONFIG

  FDC2112_Set_Reg (&fdc2114,FDC2214_RESET_DEV,0x0600);//Figure 47. Address 0x1C, RESET_DEV   600-16x 400-8x 200-4x 0000-1x

  FDC2112_Set_Reg (&fdc2114,FDC2214_DRIVE_CH0,0xF000);//11110: 1.354mA
  FDC2112_Set_Reg (&fdc2114,FDC2214_DRIVE_CH1,0xF000);//11110: 1.354mA
  FDC2112_Set_Reg (&fdc2114,FDC2214_DRIVE_CH2,0xF000);//11110: 1.354mA
  FDC2112_Set_Reg (&fdc2114,FDC2214_DRIVE_CH3,0xF000);//11110: 1.354mA

FDC2112_Get_Value_Chanel(&fdc2114,0);


FDC2112 FDC2114 FDC2212 FDC2214
