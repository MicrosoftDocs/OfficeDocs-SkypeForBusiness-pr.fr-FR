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
description: En savoir plus sur la passerelle SIP, telles que les exigences et les avantages.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f20c26d07bbfb0eebef9b46cbc1db85ad9f4d341
ms.sourcegitcommit: 30429a67cf477afa97fb09aa3b301443d989f8eb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68384740"
---
# <a name="plan-for-sip-gateway"></a>Planifier la passerelle SIP

La passerelle SIP permet à votre organisation d’utiliser n’importe quel appareil SIP compatible avec Microsoft Teams pour préserver vos investissements dans les appareils SIP. Vous pouvez maintenant vous connecter à Teams avec vos informations d’identification d’entreprise et passer et recevoir des appels avec un appareil SIP compatible. Les appareils compatibles peuvent être Skype Entreprise des téléphones IP avec microprogramme SIP standard, des téléphones IP Cisco avec microprogramme SIP multiplateforme ou des appareils SIP de fournisseurs tels que Poly, Yealink et AudioCodes. Pour savoir comment configurer vos appareils SIP pour la passerelle SIP, consultez [Configurer la passerelle SIP](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Avantages de la passerelle SIP

La passerelle SIP connecte des appareils SIP compatibles à Teams pour aider vos utilisateurs à migrer en toute transparence vers la téléphonie Teams. À l’aide de la passerelle SIP, vos utilisateurs peuvent effectuer toutes les opérations suivantes :

- **Passer des appels :** Les utilisateurs d’appareils SIP peuvent passer des appels au réseau téléphonique commuté (RTC), à d’autres appareils SIP, à Teams et à Skype Entreprise utilisateurs. Les utilisateurs d’appareils SIP peuvent uniquement appeler les utilisateurs qui ont des numéros de téléphone.
- **Recevoir des appels :** Les utilisateurs d’appareils SIP peuvent recevoir un appel du RTC, de Teams ou Skype Entreprise utilisateurs disposant d’appareils SIP, ainsi que de Teams et d’applications clientes Skype Entreprise. L’appareil SIP agit comme un point de terminaison Teams. Les appels entrants seront également dupliqués vers l’appareil SIP de l’utilisateur.
- **Plusieurs appels simultanés :** Un utilisateur d’appareil SIP dans un appel peut mettre l’appel en attente pour effectuer ou recevoir d’autres appels. Un utilisateur d’appareil SIP peut également téléconférencer deux appels.
- **Ne pas déranger :** Un utilisateur d’appareil SIP peut définir ne pas déranger sur l’appareil afin que l’appareil ne sonne pas pour les appels entrants. Cela n’a aucun impact sur l’état de l’utilisateur sur tous les autres points de terminaison Teams.
- **Hold/Resume et Mute/Unmute :** Un utilisateur d’appareil SIP peut maintenir et reprendre ou désactiver ou désactiver un appel à l’aide des fonctionnalités de ces actions sur l’appareil.
- **Messagerie vocale:** Les utilisateurs d’appareils SIP peuvent écouter les messages vocaux stockés électroniquement que les appelants quittent pour eux.
- **Indicateur d’attente de message :** Les utilisateurs d’appareils SIP peuvent recevoir des notifications qui les alertent lorsqu’ils ont de nouveaux messages vocaux.
- **Connexion et déconnexion :** Les utilisateurs d’appareils SIP peuvent se connecter et se déconnecter de Teams sur l’appareil.
- **Multifréquence à deux tonalités :** Les utilisateurs d’appareils SIP peuvent appuyer sur les touches numériques pour fournir une entrée lors des appels de réponse vocale interactifs.
- **Réunions Teams :** Un utilisateur d’appareil SIP peut rejoindre une réunion Teams en composant le numéro d’accès à la réunion. Les participants à la réunion peuvent ajouter un utilisateur d’appareil SIP à la réunion en composant le numéro de téléphone de l’utilisateur ou en ajoutant simplement un participant en cliquant sur « Demander à rejoindre » pour alerter également l’appareil SIP de l’utilisateur. Les utilisateurs invités d’une autre organisation peuvent être ajoutés à une réunion Teams par un participant qui compose le numéro d’un utilisateur invité pour inclure cet invité.
- **Transferts d’appels :** Les utilisateurs d’appareils SIP peuvent transférer des appels. La passerelle SIP prend en charge les transferts aveugles et consultatifs.
- **Transfert d’appel local :** Un utilisateur d’appareil SIP peut définir des règles de transfert (toujours, au délai d’expiration et occupé) pour l’appareil. Si l’appareil est connecté à la passerelle SIP, l’appel est redirigé vers l’adresse cible en fonction de la règle définie par l’utilisateur de l’appareil. Pour que le transfert d’appel local fonctionne, l’administrateur doit définir l’attribut `AllowCallRedirect` sur `Set-CsTeamsCallingPolicy` `Enabled`.
- **Appareils obsolètes hors-bord :** La passerelle SIP prend en charge la désintégration automatique des appareils obsolètes approvisionnés pour un locataire. Les appareils appairés (connectés) seront désintégrés s’ils ne sont pas connectés pendant 30 jours et les appareils non appariés (déconnectés) après 14 jours. Un appareil désintégré peut être réintégré après une réinitialisation d’usine.

## <a name="requirements-to-use-sip-gateway"></a>Configuration requise pour utiliser la passerelle SIP

Les utilisateurs Teams doivent disposer d’un numéro de téléphone avec l’appel RTC activé pour utiliser la passerelle SIP.

> [!NOTE]
> La passerelle SIP n’est pas disponible pour les environnements gouvernementaux (GCC, GCC High et DoD).

### <a name="hardware-software-and-licenses"></a>Matériel, logiciels et licences

Si vous disposez d’un appareil 3PIP ou SIP, vous devez disposer des éléments suivantes :

- Une licence pour Microsoft Teams, Skype Entreprise Plan en ligne 2 et Microsoft 365 Phone System (via des licences E5 ou autonomes)
- Activation RTC (par exemple, un numéro de téléphone) via un plan d’appel Microsoft Teams, un routage direct ou une connexion d’opérateur
- Une licence Common Area Phone pour tous les appareils de zone commune

## <a name="compatible-devices"></a>Appareils compatibles

|Fournisseur    |Modèle      |Version minimale du microprogramme|Version approuvée du microprogramme|Remarques|Liens|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |Les appareils exécutant le microprogramme d’entreprise doivent être convertis en microprogramme multiplateforme. Lisez le guide à droite pour savoir comment faire.|[Guide de conversion du microprogramme Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832       |11.3.5MPP   |11-3-7 MPP  |   |   |
|          |6821       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-7 MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-7 MPP  |   |   |
|**Poly**  |           |            |           |L’appareil redémarre automatiquement et installe le microprogramme sélectionné.|   |
|          |Trio 8500  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |Trio 8800  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |VVX150<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX301<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX311<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX401<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX411<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX501<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX601<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |Rove B2    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove B4    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove 30    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove 40    |8.0.3.0010  |8.0.3.0010 |   |   |
|**Yealink**|          |            |           |   |[Prise en charge de Yealink](https://support.yealink.com/)|
|          |T21P       |83          |34.72.0.75 |   |   |
|          |T21P_E2    |83          |52.84.0.125|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G<sup>1</sup>      |83          |69.86.0.15 |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30<sup>1</sup>       |83          |124.86.0.40|   |   |
|          |T30P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T33G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T41S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T43U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|          |T46S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T46U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T48U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T53<sup>1</sup>       |83          |96.86.5.1  |   |   |
|          |T53W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T54W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T57W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|**AudioCodes**|       |            |           |Certains appareils SIP AudioCodes ont besoin d’un paramètre d’URL de provisionnement. Téléchargez et installez les fichiers de mise à niveau pour les appareils AudioCodes affectés à droite. |[Fichiers téléchargeables pour les appareils affectés sur AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405<sup>1</sup>        |2.2.8      |2.2.16.589 |   |   |
|          |405HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |405HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |420HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |420HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |430HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |430HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |440HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704 |   |   |
|          |445HDG<sup>1</sup>     |3.2.1      |3.4.6.704 |   |   |
|          |450HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |C450HD<sup>1</sup>     |3.2.1      |3.4.6.704  |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |RX50<sup>1</sup>       |3.2.1      |3.4.6.704  |   |   |
|**Spectralink**|       |           |           |   |[Prise en charge de Spectraink](https://support.spectralink.com)|
|          |7202        |PCS22B     |PCS22B     |Combiné |   |
|          |7212        |PCS22B     |PCS22B     |Combiné |   |
|          |7502        |PCS22B     |PCS22B     |Combiné |   |
|          |7522        |PCS22B     |PCS22B     |Combiné |   |
|          |7532        |PCS22B     |PCS22B     |Combiné |   |
|          |7622        |PCS22B     |PCS22B     |Combiné |   |
|          |7642        |PCS22B     |PCS22B     |Combiné |   |
|          |7722        |PCS22B     |PCS22B     |Combiné |   |
|          |7742        |PCS22B     |PCS22B     |Combiné |   |
|          |IP-DECT Server 200 |PCS22Ab |PCS22Ab |Serveur IP-DECT |   |
|          |IP-DECT Server 400 |PCS22Ab |PCS22Ab |Serveur IP-DECT |   |
|          |IP-DECT Server 6500 |PCS22Ab |PCS22Ab |Serveur IP-DECT |   |
|          |Serveur IP-DECT virtuel 1 |PCS22Ab |PCS22Ab |Serveur IP-DECT |   |
|          |IP-DECT Base Station |PCS22Ab |PCS22Ab |Serveur IP-DECT |   |
|**Ascom**|       |           |           |   |[Prise en charge d’Ascom](https://www.ascom.com/products-and-services/services/support-and-maintenance/)|
|          |Ascom d43        |2.11.4     |2.11.4     |Combiné |   |
|          |Ascom d63        |2.11.4     |2.11.4     |Combiné |   |
|          |Ascom d81        |4.13.1     |4.13.1     |Combiné |   |
|          |Ascom d83        |4.13.1     |4.13.1     |Combiné |   |
|          |Ascom Myco 3 DECT        |3.4.1     |3.4.1     |Combiné |   |
|          |IPBSx du point d’accès IP-DECT        |11.8.8     |11.8.8     |Point d’accès IP-DECT |   |
|          |IP-DECT Gateway IPBL     |11.8.8     |11.8.8     |Passerelle IP-DECT |   |
|          |TDM Base Station        |R3N     |R3N     |IP-DECT Base Station |   |
|          |IPVM de l’appliance virtuelle IP-DECT        |11.8.8     |11.8.8     |Serveur IP-DECT |   |

<sup>1 L’appareil</sup> prend en charge les appels d’urgence dynamiques (E911) avec la passerelle SIP.

> [!NOTE]
> Les clients peuvent utiliser AudioCodes OVOC et Poly Lens pour gérer la configuration côté appareil de leurs appareils AudioCodes 400 et Poly VVX/Trio, respectivement.

> [!NOTE]
> Les appareils Spectrasink reçoivent les mises à jour du microprogramme en direct des serveurs IP-DECT DeCt de Specink.

> [!NOTE]
> Les combinés Ascom reçoivent les mises à jour du microprogramme en direct des serveurs Ascom IP-DECT.

> [!NOTE]
> Pour les requêtes de support, les clients qui utilisent des systèmes IP-DECT avec la passerelle SIP Teams doivent contacter leur fabricant DECT ou leurs partenaires de canal d’implémentation.

> [!NOTE]
> Pour certains appareils, la version minimale du microprogramme est supérieure à la version approuvée du microprogramme. Cela est dû au fait que la version 3.X est la version Skype Entreprise. Nous mettons à jour la version SIP 2.X.
