---
title: Planifier la passerelle SIP
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: En savoir plus sur la passerelle SIP, telles que la exigences et les avantages.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 817f3dc7ce7f0b6f407607417c0cadb92b65e943
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514749"
---
# <a name="plan-for-sip-gateway"></a>Planifier la passerelle SIP

La passerelle SIP permet à votre organisation d’utiliser n’importe quel appareil SIP compatible avec Microsoft Teams pour préserver vos investissements dans les appareils SIP. Vous pouvez désormais vous Teams connexion à l’aide de vos informations d’identification professionnelles et passer et recevoir des appels avec un appareil SIP compatible. Les appareils compatibles peuvent être des Skype Entreprise IP avec microprogramme SIP standard, des téléphones IP Cisco avec microprogramme SIP à plusieurs plateformes ou des appareils SIP de fournisseurs tels que Poly, Yealink et AudioCodes. Pour découvrir comment configurer vos appareils SIP pour la passerelle SIP, voir [Configurer la passerelle SIP](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Avantages de la passerelle SIP

La passerelle SIP connecte des appareils SIP compatibles à des Teams pour aider vos utilisateurs à migrer facilement vers Teams téléphonie. Avec la passerelle SIP, vos utilisateurs peuvent :

- **Appels :** Les utilisateurs de l’appareil SIP peuvent passer des appels vers le réseau téléphonique public commuté (PSTN), vers d’autres appareils SIP, ainsi qu Teams et Skype Entreprise utilisateurs. Les utilisateurs d’un appareil SIP peuvent uniquement appeler les utilisateurs phonant des numéros de téléphone.
- **Recevoir des appels :** Les utilisateurs d’un appareil SIP peuvent recevoir un appel d’un réseau PSTN, d’utilisateurs de Teams ou d’Skype Entreprise qui utilisent des appareils SIP, et d’applications clientes Teams et Skype Entreprise client. L’appareil SIP agit comme un point de Teams de terminaison. Les appels entrants sont également dus à l’appareil SIP de l’utilisateur.
- **Plusieurs appels simultanés :** Un utilisateur de l’appareil SIP d’un appel peut mettre l’appel en attente pour passer ou recevoir d’autres appels. Un utilisateur de périphérique SIP peut également se lire deux appels de conférence.
- **Ne pas déranger :** Un utilisateur de l’appareil SIP peut définir ne pas déranger sur l’appareil de sorte que l’appareil ne sonne pas pour les appels entrants. Cela n’a aucune incidence sur l’état de l’utilisateur sur tous les Teams points de terminaison.
- **Mettre en attente/Reprendre et désactiver le son/Réactiver le son :** Un utilisateur de périphérique SIP peut maintenir, reprendre ou désactiver ou réactiver le son d’un appel en utilisant les fonctionnalités de ces actions sur l’appareil.
- **Messagerie vocale :** Les utilisateurs de périphérique SIP peuvent écouter les messages vocaux stockés électroniquement que les appelants laissent pour eux.
- **Indicateur de message en attente :** Les utilisateurs de l’appareil SIP peuvent recevoir des notifications qui les avertissent lorsqu’ils reçoivent de nouveaux messages vocaux.
- **Se connectez et se connectez :** Les utilisateurs d’appareils SIP peuvent se connecter et se Teams’utiliser sur l’appareil.
- **Fréquence multifréquence à deux fréquences :** Les utilisateurs de l’appareil SIP peuvent appuyer sur les touches numériques pour fournir une entrée pendant les appels de réponse vocale interactifs.
- **Teams réunions :** un utilisateur de l’appareil SIP peut participer Teams réunion en composant le numéro d’accès à la réunion. Les participants à la réunion peuvent ajouter un utilisateur d’appareil SIP à la réunion en composant un numéro de téléphone d’utilisateur ou en ajoutant simplement un participant en cliquant sur « Demander à rejoindre » pour avertir également l’appareil SIP de l’utilisateur. Les utilisateurs invités d’une autre organisation peuvent être ajoutés à une réunion Teams par un participant qui compose le numéro d’un utilisateur invité pour l’inclure.
- **Transferts d’appel :** Les utilisateurs de l’appareil SIP peuvent transférer des appels. La passerelle SIP prend en charge les transferts non voyants et consultatifs.
- **Forwarding d’appel local :** Un utilisateur de l’appareil SIP peut définir des règles de forwarding (toujours, au délai d’délai et occupés) pour l’appareil. Si l’appareil est connecté à la passerelle SIP, l’appel est redirigé vers l’adresse cible en fonction de la règle définie par l’utilisateur de l’appareil. Pour que le forwarding d’appel local fonctionne, l’administrateur doit définir l’attribut `AllowCallRedirect` sur `Set-CsTeamsCallingPolicy` `Enabled`. 


## <a name="requirements-to-use-sip-gateway"></a>Conditions requises pour utiliser la passerelle SIP

Teams utilisateurs doivent avoir un numéro de téléphone avec la passerelle DNS activée pour utiliser la passerelle SIP.

### <a name="hardware-software-and-licenses"></a>Matériel, logiciels et licences

Si vous avez un appareil SIP ou 3PIP, vous devez avoir : 
- Une licence pour Système téléphonique (via un E5 ou une licence autonome)
- l’enablement RSTN (c’est-à-dire, un numéro de téléphone) via un plan d’appel Microsoft Teams, un routage direct ou un numéro d’Connecter
- Licence Zone commune Téléphone’appareils en zone commune

## <a name="compatible-devices"></a>Appareils compatibles

|Fournisseur    |Modèle      |Version minimale du microprogramme|Version de microprogramme approuvée|Remarques|Liens|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |Les appareils exécutant un microprogramme d’entreprise doivent être convertis en microprogramme à plusieurs plateformes. Pour savoir comment faire, lisez le guide à droite.|[Guide de conversion du microprogramme de Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832       |11.3.5MPP   |11.3.5MPP  |   |   |
|          |6821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-3MPP  |   |   |
|**Poly**  |           |            |           |L’appareil redémarrera automatiquement et installera le microprogramme sélectionné.|   |
|          |Monde 8500  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |Monde 8800  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |VVX150     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601     |5.9.5       |6.3.1.8427 |   |   |
|**Yealink**|          |            |           |   |[Prise en charge de Yealink](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U       |83          |108.86.0.20|   |   |
|          |T43U       |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U       |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U       |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**AudioCodes**|       |            |           |Certains appareils AUDIOCodes SIP ont besoin d’un paramètre d’URL d’approvisionnement. Téléchargez et installez des fichiers de mise à niveau pour les périphériques AudioCodes concernés sur la droite. |[Fichiers téléchargeables pour les appareils concernés sur AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405         |2.2.8      |2.2.16.570 |   |   |
|          |405HD       |3.2.1      |2.2.16.570 |   |   |
|          |420HD       |3.2.1      |2.2.16.570 |   |   |
|          |430HD       |3.2.1      |2.2.16.570 |   |   |
|          |440HD       |3.2.1      |2.2.16.570 |   |   |
|          |450HD       |3.2.1      |3.4.6.687  |   |   |
|          |C450HD      |3.2.1      |3.4.6.687  |   |   |
|          |445HD       |3.2.1      |3.4.6.687  |   |   |
|          |RX50        |3.2.1      |3.4.6.687  |   |   |

> [!NOTE]
> Pour certains appareils, la version minimale du microprogramme est supérieure à la version approuvée du microprogramme. Cela est dû au fait que la version 3.X est Skype Entreprise version complète. Nous avons mis à jour la version SIP 2.X.
