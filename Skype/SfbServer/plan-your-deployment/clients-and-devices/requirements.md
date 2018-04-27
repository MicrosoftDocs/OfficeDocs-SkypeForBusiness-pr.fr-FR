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
description: Cet article résume la configuration requise pour prendre en charge un v2 Skype salle systèmes.
ms.openlocfilehash: 6b0265c8fc6269b7451a7757b8266078433ec9d5
ms.sourcegitcommit: 5cc51e2d3898fccd1969accedb5e185a332e83bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2018
---
# <a name="skype-room-systems-v2-requirements"></a>Configuration requise pour Skype Room Systems v2
 
Cet article résume la configuration requise pour prendre en charge un v2 Skype salle systèmes. 
  
Votre déploiement implique la création de compte comme décrit dans [déployer Skype salle systèmes v2](../../deploy/deploy-clients/room-systems-v2.md) et la configuration d’une console de réunion, comme indiqué dans [Configure une console v2 de systèmes de salle Skype](../../deploy/deploy-clients/console.md). Vous devez également faire référence à [Skype pour les licences d’entreprise module complémentaire](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).
  
## <a name="hardware-requirements"></a>Configuration matérielle requise

Systèmes de salle Skype v2 capable de s’adapter aux tailles différentes salles au moyen d’accessoires selon les périphériques audio et vidéo. Les périphériques audio et vidéo se connecter à v2 Skype salle systèmes via une connexion USB ou HDMI sur le périphérique d’accueil. Vous aurez également besoin des éléments suivants :
  
- 32 Go de disque de plus grande capacité USB, vous allez configurer en tant que le support d’installation Windows pour Windows 10 Enterprise. 
    
- Parmi les tablettes suivantes :
    
**Tablettes pris en charge**


|**Tablet PC**|**Processeur**|**MÉMOIRE RAM**|**Disque**|
|:-----|:-----|:-----|:-----|
|Surface Pro 4 & sup1 ;  <br/> |Principaux i5  <br/> |4 GO  <br/> |128 GO  <br/> |
|Surface Pro 4 & sup1 ;  <br/> |Principaux i5  <br/> |8 GO  <br/> |256 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Principaux i5  <br/> |4 GO  <br/> |128 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Principaux i5  <br/> |8 GO  <br/> |256 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Core i7  <br/> |8 GO  <br/> |128 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Core i7  <br/> |16 GO  <br/> |512 GO  <br/> |
|Surface Pro & sup1 ; <br/> |Core i7  <br/> |16 GO  <br/> |1 TO  <br/> |
   
& sup1 ; — M3 processeurs ne sont pas pris en charge sur ce modèle.
    
 
    
- Une des options de la station d’accueil suivantes pour sécuriser la tablette à la réunion de l’espace table. 
    
  - [Logitech SmartDock](https://www.logitech.com/en-us/product/smartdock)
    
  - [SR Crestron](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
    
  - [Série de Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

  - [Hub Lenovo 500](https://www3.lenovo.com/us/en/hub500)  
<!-- HP dock is still pending  -->  
 
**Certifié versions du microprogramme pour les périphériques audio et vidéos USB**
|**Périphériques v2 de systèmes de salle de Skype**|**Version de microprogramme certifiée pour les systèmes de salle Skype v2**|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> ||
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio - 1.0.172  <br/> Vidéo - 1.0.156  <br/> |
|[Logitech ConferenceCam se connecter](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Groupe Logitech](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Trois RealPresence de Polycom](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[CX5100 de Polycom](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[510 Jabra](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |
   
- **Extensions USB**:
    
  - Ports USB s’ancre Tablet PC sont 3.0 USB compatible. Vous pouvez utiliser une extension 2.x USB, mais cela donc limitera à la vitesse de 2.x USB sur l’extrémité et cela n’est donc pas recommandé pour les périphériques USB 3.0.
    
  - Une extension doit satisfaire USB 2.0 ou des spécifications plus récentes.
    
  - S’ancre Tablet PC prend en charge au moins deux étapes de l’extension du concentrateur USB externe. Si nécessaire pour se connecter plus de deux concentrateurs USB de série, vous devrez contactez le fabricant de la station d’accueil pour vérifier cela donc est pris en charge.
    
- Connexion câblée Gigabit dans la salle. Câble Ethernet de longueur appropriée.
    
- Affiche 1080p jusqu'à deux connexions HDMI. Câbles HDMI de longueur appropriée.
    
    > [!NOTE]
    > Télévision utilisée comme un plan de salle d’affichage pour la prise en charge/activer la fonctionnalité de contrôle de Electronics consommateur (CCE) de HDMI afin qu’il peut basculer automatiquement à une source vidéo active du mode veille. Cette fonctionnalité n’est pas pris en charge sur tous les TV. 
  
> [!NOTE]
> Systèmes de salle Skype v2 n’utilise pas un clavier. Si nécessaire, l’administrateur doit utiliser le clavier visuel. Un clavier ou souris USB seront requise lors de l’appareil v2 Skype salle systèmes d’imagerie. 
  
Les tableaux suivants fournissent des recommandations pour les périphériques en fonction de la taille de la pièce :
  
**Salle Skype systèmes v2 certifié périphériques Audio**

|**Type de salle**|**Nombre de personnes**|**Distance maximale recommandée à partir d’un microphone à personne de parler**|**Périphérique par la taille maximale de salle**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  <br/> |2 à 4  <br/> |1,5 m  <br/> |Logitech Connect  <br/> |Les périphériques Logitech connecter incluent une caméra doit être positionné au début de la salle (pas le centre de table) pour capturer les participants à la réunion local.  <br/> |
|**Petite taille** <br/> 16' x 16'  <br/> |4-6  <br/> |m 2.0  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |Le volume de lecture peut être limité pour des salles plus grandes.  <br/> |
|**Taille moyenne** <br/> 18' x 20'  <br/> |6-12  <br/> |2,4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |Le Logitech MeetUp inclut une caméra afin qu’il doit se situer sur le plan de salle (pas le centre de table pour capturer les participants à la réunion local).  <br/> En règle générale, les salles de tables longues rectangulaires ou en forme de u peuvent bénéficier de microphones satellite supplémentaires.  <br/> SP 220 MS doit être utilisé dans une configuration en chaîne.  <br/> |
|**Grande taille** <br/> 15' x 20'  <br/> |12-16  <br/> |3M  <br/> La distance s’applique également à la zone couverte par chaque microphone satellite supplémentaire connecté au périphérique audio en question.   <br/> |Groupe Logitech + micros satellites  <br/> Trois Polycom + satellites micros  <br/> Polycom CX5100 + micros satellites  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + micros satellites  <br/> |Tous les périphériques audio répertoriés dans cette ligne prennent en charge les options de microphone satellite.  <br/> CX5100 comprend une caméra 360 degrés intégrée de manière à ce que le périphérique puisse être positionné au centre de la table.  <br/> SP 220 MS doit être utilisé dans une configuration en chaîne.  <br/> |
   
**Salle Skype systèmes v2 certifié périphériques vidéo**

|**Type de salle**|**Nombre de personnes**|**Périphérique par taille optimale de salle**|**Commentaires**|
|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  <br/> |2 à 4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**Petite taille** <br/> 16' x 16'  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> MSR Polycom  <br/> Polycom CX5100   <br/> |Logitech PTZ Pro souvent fourni avec le groupe Logitech  <br/> |
|**Taille moyenne** <br/> 18' x 20'  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> MSR Polycom  <br/> Polycom CX5100   <br/> ||
|**Grande taille** <br/> 15' x 20'  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> MSR Polycom  <br/> Polycom CX5100   <br/> ||
   
## <a name="required-software-downloads"></a>Téléchargement des logiciels requis

Vous devez les téléchargements pour créer votre propre image v2 de Skype salle systèmes suivants :
  
- Le [package d’installation de systèmes de salle Skype v2](https://go.microsoft.com/fwlink/?linkid=851168).
    
- Obtenez une copie de la version 64 bits de mise à jour du créateur de contenu d’entreprise 10 Windows (en anglais, build 1703). 
    
    > [!NOTE]
    > La version 64 bits de l’édition entreprise anniversaire de mariage 10 Windows (en anglais, version 1607) n’est plus pris en charge à partir de systèmes de salle Skype v2 version 3.0.12.0 (mise à jour 3). 
  
- La prise en charge [4 Surface Pro pilotes](https://go.microsoft.com/fwlink/?linkid=856887) ou des [pilotes Surface Pro](https://go.microsoft.com/fwlink/?linkid=856888).
    
Ces téléchargements doivent combiner un disque amorçable de support d’installation Windows de façon spécifique, décrites dans [Configure une console v2 de systèmes de salle Skype](../../deploy/deploy-clients/console.md). 
  
En outre, vous souhaiterez probablement une copie du [script Powershell](https://go.microsoft.com/fwlink/?linkid=870105) utilisé pour configurer les comptes Skype salle systèmes v2.
  
## <a name="see-also"></a>Voir aussi

#### 

[Planifier la salle Skype systèmes v2](skype-room-systems-v2-0.md)
  
[Déployer la salle Skype systèmes v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurer une console v2 de systèmes de salle de Skype](../../deploy/deploy-clients/console.md)
  
[Gérer les salles Skype systèmes v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
#### 

[Licences de module complémentaire Skype Entreprise](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)

