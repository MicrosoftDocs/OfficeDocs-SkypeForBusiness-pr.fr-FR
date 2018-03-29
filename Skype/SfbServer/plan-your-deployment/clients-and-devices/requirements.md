---
title: Configuration requise pour Skype Room Systems v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
description: Cet article récapitule la configuration requise pour la prise en charge d’un v2 de systèmes de salle de Skype.
ms.openlocfilehash: ca922efa719b956da5516958ce6f684b013ddc62
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-systems-v2-requirements"></a>Configuration requise pour Skype Room Systems v2
 
Cet article récapitule la configuration requise pour la prise en charge d’un v2 de systèmes de salle de Skype. 
  
Votre déploiement implique la création de compte comme décrit dans le [déploiement de systèmes de salle Skype v2](../../deploy/deploy-clients/room-systems-v2.md) et configuration d’une console de réunion comme décrit dans [configuration d’une console de v2 Skype salle de systèmes](../../deploy/deploy-clients/console.md). Vous devez également faire référence à [Skype pour la licence de module complémentaire Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).
  
## <a name="hardware-requirements"></a>Configuration matérielle requise

Systèmes de salle Skype v2 peut s’adapter à des tailles de pièce au moyen d’accessoires selon les périphériques audio et vidéo. Les périphériques audio et vidéo se connectent à v2 Skype salle systèmes via une connexion USB ou HDMI sur le périphérique d’accueil. Vous aurez également besoin des éléments suivants :
  
- Un disque de plus grande capacité USB ou de 32 Go, vous allez configurer comme support d’installation Windows pour Windows 10 Enterprise. 
    
- Parmi les tablettes suivantes :
    
**Prise en charge de Tablet PC**


|**Tablet PC**|**Processeur**|**MÉMOIRE VIVE**|**Disque**|
|:-----|:-----|:-----|:-----|
|Surface Pro 4 & sup1 ;  <br/> |Core i5  <br/> |4 GO  <br/> |128 GO  <br/> |
|Surface Pro 4 & sup1 ;  <br/> |Core i5  <br/> |8 GO  <br/> |256 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Core i5  <br/> |4 GO  <br/> |128 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Core i5  <br/> |8 GO  <br/> |256 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Core i7  <br/> |8 GO  <br/> |128 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Core i7  <br/> |16 GO  <br/> |512 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Core i7  <br/> |16 GO  <br/> |1 TO  <br/> |
   
& sup1 ; — M3 processeurs ne sont pas pris en charge sur ce modèle.
    
 
    
- Une des options de la station d’accueil suivantes pour sécuriser la tablette à la réunion de l’espace table. 
    
  - [Logitech SmartDock](https://www.logitech.com/en-us/product/smartdock)
    
  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
    
  - [Série de Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)

  - [Concentrateur de Lenovo 500](https://www3.lenovo.com/us/en/hub500)  
<!-- HP dock is still pending  -->  
 
**Certifié des versions de logiciel pour les périphériques USB audio et vidéo**
|**Périphériques de systèmes de salle Skype v2**|**Version du firmware certifiée pour systèmes de salle Skype v2**|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> ||
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio - 1.0.172  <br/> Vidéo - 1.0.156  <br/> |
|[ConferenceCam de Logitech vous connecter](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Groupe de Logitech](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Trio de RealPresence de Polycom](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[CX5100 de Polycom](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |
   
- **Rallonge USB**:
    
  - Les ports USB sur les stations d’accueil de Tablet PC sont 3.0 de USB compatible. Vous pouvez utiliser un extendeur 2.x USB, mais cela donc vous contraignent à vitesse de 2.x USB sur l’extrémité et cela n’est donc pas recommandé pour les périphériques USB 3.0.
    
  - Un extendeur doit satisfaire USB 2.0 ou spécifications plus récentes.
    
  - Stations d’accueil de Tablet PC prend en charge au moins deux étapes de l’extension de concentrateur USB externe. Si nécessaire pour vous connecter plus de deux concentrateurs USB de série, vous devez vérifier auprès du fabricant de la station d’accueil pour confirmer cela donc est pris en charge.
    
- Connexion Gigabit Ethernet filaire dans la salle. Câble Ethernet de longueur appropriée.
    
- Affiche les 1080p jusqu'à deux connexions de HDMI. Câbles HDMI de longueur appropriée.
    
    > [!NOTE]
    > Un poste de télévision utilisé comme frontal de salle d’affichage pour la prise en charge/activer la fonctionnalité de contrôle des appareils électroniques grand public (CEC) de HDMI afin qu’il peut basculer automatiquement vers une source vidéo active du mode veille. Cette fonctionnalité n’est pas pris en charge sur tous les téléviseurs. 
  
> [!NOTE]
> Systèmes de salle Skype v2 n’utilise pas d’un clavier. Si nécessaire, l’administrateur doit utiliser le clavier visuel. Un clavier USB ou une souris sera nécessaire lorsque le dispositif de v2 Skype salle systèmes d’imagerie. 
  
Les tableaux suivants fournissent des recommandations pour les périphériques en fonction de la taille de la pièce :
  
**Salle de Skype v2 de systèmes certifiés des périphériques Audio**

|**Type de chambre**|**Nombre de personnes**|**Distance maximale recommandée de microphone à personne parler**|**Périphérique par la taille maximale de pièce**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  <br/> |2-4  <br/> |1,5 m  <br/> |Logitech Connect  <br/> |Les périphériques de connexion de Logitech incluent un appareil photo doit être positionné à l’avant de la pièce (pas au centre de la table) pour capturer les participants à la réunion locale.  <br/> |
|**Petite taille** <br/> 16' x 16'  <br/> |4-6  <br/> |2.0m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |Le volume de lecture peut être limité pour des salles plus grandes.  <br/> |
|**Support** <br/> 18' x 20'  <br/> |6-12  <br/> |2,4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |Le Logitech MeetUp comprend une caméra et il doit être situé à l’avant de la pièce (pas au centre de la table pour capturer des participants à la réunion locale).  <br/> En général, les salles de tables longs ou rectangulaires en forme de u peuvent bénéficier de microphones satellite supplémentaire.  <br/> SP 220 MS doit être utilisé dans une configuration en chaîne.  <br/> |
|**Grande taille** <br/> 15' x 20'  <br/> |12-16  <br/> |3m  <br/> La distance s’applique également à la zone couverte par chaque microphone satellite supplémentaire connecté au périphérique audio en question.   <br/> |Groupe de Logitech + micros de satellite  <br/> Trio de Polycom + micros de satellite  <br/> Polycom CX5100 + micros de satellite  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + micros de satellite  <br/> |Tous les périphériques audio répertoriés dans cette ligne prennent en charge les options de microphone satellite.  <br/> CX5100 comprend une caméra 360 degrés intégrée de manière à ce que le périphérique puisse être positionné au centre de la table.  <br/> SP 220 MS doit être utilisé dans une configuration en chaîne.  <br/> |
   
**Salle de Skype v2 de systèmes certifiés des périphériques vidéo**

|**Type de chambre**|**Nombre de personnes**|**Périphérique par la taille de la pièce optimale**|**Commentaires**|
|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**Petite taille** <br/> 16' x 16'  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> MSR de Polycom  <br/> Polycom CX5100   <br/> |Logitech PTZ Pro souvent fourni avec le groupe de Logitech  <br/> |
|**Support** <br/> 18' x 20'  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> MSR de Polycom  <br/> Polycom CX5100   <br/> ||
|**Grande taille** <br/> 15' x 20'  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> MSR de Polycom  <br/> Polycom CX5100   <br/> ||
   
## <a name="required-software-downloads"></a>Téléchargement des logiciels requis

Vous devrez les téléchargements suivants pour créer votre propre image v2 de systèmes de salle de Skype :
  
- Le [package d’installation de systèmes de salle Skype v2](https://go.microsoft.com/fwlink/?linkid=851168).
    
- Obtenir une copie de la version 64 bits de mise à jour de Windows 10 entreprise créateur (en langue anglaise, build 1703). 
    
    > [!NOTE]
    > La version 64 bits de l’édition Windows 10 entreprise anniversaire (en langue anglaise, version 1607) n’est plus pris en charge à partir de systèmes de salle Skype v2 version 3.0.12.0 (mise à jour 3). 
  
- La prise en charge [4 de Surface Pro pilotes](https://go.microsoft.com/fwlink/?linkid=856887) ou des [pilotes de Surface Pro](https://go.microsoft.com/fwlink/?linkid=856888).
    
Ces téléchargements doivent être combinés en un disque amorçable de support d’installation Windows d’une manière spécifique, décrite plus loin dans la [configuration d’une console de v2 Skype salle de systèmes](../../deploy/deploy-clients/console.md). 
  
En outre, vous souhaiterez probablement une copie du [script Powershell](https://go.microsoft.com/fwlink/?linkid=870105) permet de mettre en service les comptes Skype salle systèmes v2.
  
## <a name="see-also"></a>Voir aussi

#### 

[Plan de salle de Skype systèmes v2](skype-room-systems-v2-0.md)
  
[Déployer Skype salle systèmes v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurer une console v2 de systèmes de salle de Skype](../../deploy/deploy-clients/console.md)
  
[Gérer l’espace de Skype systèmes v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
#### 

[Licences de module complémentaire Skype Entreprise](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)

