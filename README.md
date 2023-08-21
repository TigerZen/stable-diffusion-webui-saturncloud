🐣 Please follow me for new updates https://twitter.com/camenduru <br />
🔥 Please join our discord server https://discord.gg/k5BwmmvJJU <br />
🥳 Please join my patreon community https://patreon.com/camenduru <br />

## Tutorial
https://www.youtube.com/watch?v=NJ-uV5GHN8g <br />

## Jupyter Notebooks

[![Run in Saturn Cloud](https://saturncloud.io/images/embed/run-in-saturn-cloud.svg)](https://app.community.saturnenterprise.io/dash/o/community/resources?templateId=af7183683ef2475c9ef8f795b5bc735a)

| Jupyter Notebook | Info
| --- | --- |
[sdxl_v1.0_webui_saturncloud](sdxl_v1.0_webui_saturncloud.md) | [stabilityai/stable-diffusion-xl-base-1.0](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0)
[cyberrealistic_v3.2_webui_saturncloud](cyberrealistic_v3.2_webui_saturncloud.md) | [Cyberdelia/cyberrealistic](https://civitai.com/models/15003/cyberrealistic)
[sd_v1.5_controlnet_webui_saturncloud](sd_v1.5_controlnet_webui_saturncloud.md) | [runwayml/stable-diffusion-v1-5](https://huggingface.co/runwayml/stable-diffusion-v1-5)

#### Jupyter Notebook Without Tunnel (CyberRealistic v3.2) (Thanks to @tcmaps for the info ❤)
```py
%cd /home/jovyan/workspace
%env TF_CPP_MIN_LOG_LEVEL=1

!git clone -b v2.5 https://dagshub.com/camenduru/ui

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/embed/upscale/resolve/main/4x-UltraSharp.pth -d /home/jovyan/workspace/ui/models/ESRGAN -o 4x-UltraSharp.pth

!git clone https://github.com/camenduru/tunnels /home/jovyan/workspace/ui/extensions/tunnels

!git clone https://github.com/etherealxx/batchlinks-webui /home/jovyan/workspace/ui/extensions/batchlinks-webui

!git clone https://github.com/kohya-ss/sd-webui-additional-networks /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks

!git clone https://github.com/civitai/sd_civitai_extension /home/jovyan/workspace/ui/extensions/sd_civitai_extension

!git clone https://github.com/zanllp/sd-webui-infinite-image-browsing /home/jovyan/workspace/ui/extensions/sd-webui-infinite-image-browsing

!git clone https://github.com/Scholar01/sd-webui-mov2mov /home/jovyan/workspace/ui/extensions/sd-webui-mov2mov

%cd /home/jovyan/workspace/ui
!git reset --hard
!git -C /home/jovyan/workspace/ui/repositories/stable-diffusion-stability-ai reset --hard

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/GeminiX/resolve/main/geminixMix_V1.safetensors -d /home/jovyan/workspace/ui/models/Stable-diffusion -o geminixMix_V1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/GeminiX/resolve/main/geminixMix_V2.safetensors -d /home/jovyan/workspace/ui/models/Stable-diffusion -o geminixMix_V2.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/GeminiX/resolve/main/geminixMix_V3.safetensors -d /home/jovyan/workspace/ui/models/Stable-diffusion -o geminixMix_V3.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_01TaiwanDollLikeness_v15.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_01TaiwanDollLikeness_v15.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_02japanesedolllikenessV1_v15.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_02japanesedolllikenessV1_v15.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_03koreandolllikenessV20_v20.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_03koreandolllikenessV20_v20.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_04RussianDollLikeness_v3.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_04RussianDollLikeness_v3.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_05ChineseDoll_chinesedolllikeness1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_05ChineseDoll_chinesedolllikeness1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_06小V無辜臉promptsgirl_v3.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_06小V無辜臉promptsgirl_v3.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_07少女感shojovibe_v11.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_07少女感shojovibe_v11.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_08日本雜誌女星風jpIDOL_v10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_08日本雜誌女星風jpIDOL_v10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_09日風雜誌正妹momoGirls_v30.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_09日風雜誌正妹momoGirls_v30.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_10清純女孩cuteGirlMix4_v10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_10清純女孩cuteGirlMix4_v10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/00_11清純臉Nvshen_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 00_11清純臉Nvshen_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_666_AAV-nozomi2.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_666_AAV-nozomi2.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_666_AAV-rei2.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_666_AAV-rei2.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_666_AVID-mioV4.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_666_AVID-mioV4.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_666_AVID-miura.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_666_AVID-miura.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_666_CBAV-kaoru.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_666_CBAV-kaoru.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_668_AAG-hazuki.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_668_AAG-hazuki.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_668_CBCV-ran2.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_668_CBCV-ran2.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_669_77_mo.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_669_77_mo.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_七森aiAVRIRIXX_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_七森aiAVRIRIXX_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_三上aiAVYUAXx_mediumCloseUpVer.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_三上aiAVYUAXx_mediumCloseUpVer.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_沖田杏梨JAV_Anri_O_v1.0.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_沖田杏梨JAV_Anri_O_v1.0.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_松下纱荣子JAV_Saeko_M_v1.0.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_松下纱荣子JAV_Saeko_M_v1.0.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_河北彩花saikaKawakita_saikaV30.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_河北彩花saikaKawakita_saikaV30.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_宮下aiAVRENAXx_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_宮下aiAVRENAXx_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_根aiGRAVNAGIXx_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_根aiGRAVNAGIXx_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日_桃乃木aiAVKANAXxx_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日_桃乃木aiAVKANAXxx_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日星山田佳奈grav-kana.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日星山田佳奈grav-kana.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日星安潔拉芽衣angela mei.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日星安潔拉芽衣angela mei.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日星青山渚aoyamanagisa_lora-05.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日星青山渚aoyamanagisa_lora-05.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日星宮下玲奈av-rena.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日星宮下玲奈av-rena.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日星檜山沙耶hiyamasaya_lora-05.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日星檜山沙耶hiyamasaya_lora-05.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日星濱邊美波MinamiNamabe_v11.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日星濱邊美波MinamiNamabe_v11.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日星GRAV-Moii.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日星GRAV-Moii.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日星MIZUSHIMA ANJOU v2.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日星MIZUSHIMA ANJOU v2.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_0人物風格_日深田恭子fukadakyouko_lora-07.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_0人物風格_日深田恭子fukadakyouko_lora-07.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星卢正义Roh jeong eui_v10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星卢正义Roh jeong eui_v10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星申有娜YunaItzy_v2.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星申有娜YunaItzy_v2.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星申留眞RyujinITZY_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星申留眞RyujinITZY_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星安兪真iveYUJIN_yujinV1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星安兪真iveYUJIN_yujinV1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星朴芝妍Jiyeon_V30.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星朴芝妍Jiyeon_V30.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星朴彩英RoseBlackpink_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星朴彩英RoseBlackpink_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星朴善慧YurisaLora_v20.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星朴善慧YurisaLora_v20.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星李彩領ChaeryeongItzy_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星李彩領ChaeryeongItzy_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星金玟周mjftwv2.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星金玟周mjftwv2.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星金雪炫SeolhyunFromAOA_v10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星金雪炫SeolhyunFromAOA_v10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星金喜善Kim hee sun_v10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星金喜善Kim hee sun_v10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星高允貞goYoonJung_v10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星高允貞goYoonJung_v10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星崔乂園arin_V10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星崔乂園arin_V10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星張員瑛jangWonYoung_jwyV10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星張員瑛jangWonYoung_jwyV10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星裴秀智suzy_V20.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星裴秀智suzy_V20.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星潤娥Yoona_V10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星潤娥Yoona_V10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星Irene_V50.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星Irene_V50.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星JennieBlackpink_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星JennieBlackpink_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星LisaBlackpink_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星LisaBlackpink_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓星sanatwicev1-000008.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓星sanatwicev1-000008.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓國正妹kbeauKoreanBeauty_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓國正妹kbeauKoreanBeauty_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_1人物風格_韓國Coser_張娜英HinaIAmYoung22_zny10.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_1人物風格_韓國Coser_張娜英HinaIAmYoung22_zny10.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_2人物風格_外國bellaHadid_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_2人物風格_外國bellaHadid_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_2人物風格_外國Dasha.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_2人物風格_外國Dasha.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_2人物風格_外國elizabeth_olsen_v2.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_2人物風格_外國elizabeth_olsen_v2.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_2人物風格_外國EvanRachelWood23Apr.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_2人物風格_外國EvanRachelWood23Apr.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_2人物風格_外國gigiHadid_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_2人物風格_外國gigiHadid_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_2人物風格_外國LivTyler.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_2人物風格_外國LivTyler.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_2人物風格_外國tessaFowler_v1.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_2人物風格_外國tessaFowler_v1.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/TigerZen/LoRA20230821/resolve/main/01_2人物風格_外國Yvonne Strahovski.safetensors -d /home/jovyan/workspace/ui/extensions/sd-webui-additional-networks/models/lora -o 01_2人物風格_外國Yvonne Strahovski.safetensors

!sed -i -e '''/from modules import launch_utils/a\import os''' /home/jovyan/workspace/ui/launch.py
!sed -i -e '''/        prepare_environment()/a\        os.system\(f\"""sed -i -e ''\"s/dict()))/dict())).cuda()/g\"'' /home/jovyan/workspace/ui/repositories/stable-diffusion-stability-ai/ldm/util.py""")''' /home/jovyan/workspace/ui/launch.py
!sed -i -e 's/\["sd_model_checkpoint"\]/\["sd_model_checkpoint","sd_vae","CLIP_stop_at_last_layers"\]/g' /home/jovyan/workspace/ui/modules/shared.py

%cd /home/jovyan/workspace/ui
!python launch.py --listen --xformers --enable-insecure-extension-access --theme dark --gradio-queue --disable-safe-unpickle --port 8000
```

![Screenshot 2023-08-09 021455](https://github.com/camenduru/stable-diffusion-webui-saturncloud/assets/54370274/10e001b9-397c-45b6-851d-b4dc67612ee9)
![40GB](https://github.com/camenduru/fooocus-saturncloud/assets/54370274/26291759-fa0b-4041-8a62-25c234695770)

## Advanced Tutorial
[Advanced Tutorial](advanced.md)

## Stable Diffusion Web UI
https://github.com/AUTOMATIC1111/stable-diffusion-webui (Thanks to @AUTOMATIC1111 ❤)

## Documentation
https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki

## Special Thanks
Thanks to @nagikoru for the suggestion ❤
