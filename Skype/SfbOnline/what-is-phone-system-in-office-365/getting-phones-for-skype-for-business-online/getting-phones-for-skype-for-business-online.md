---
title: Obtention de numéros de téléphone pour Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 91f2d947-45fc-4fab-bd8b-2e313531c477
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Découvrez quels téléphones fonctionnent avec Skype Entreprise à partir de Polycom, HP et Mitel, ainsi que les licences requises. '
ms.openlocfilehash: 4b4a5e48a531a694b006126221ddc7fcba40e1c3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013148"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obtention de numéros de téléphone pour Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

Skype Entreprise Online qualifie et prend en charge les téléphones de bureau pour les utilisateurs qui souhaitent une expérience téléphonique traditionnelle, plutôt que d’utiliser l’application Skype Entreprise. Cette rubrique couvre les téléphones et les versions de microprogramme pris en charge pour une utilisation dans Skype Entreprise Online et d’autres informations qui peuvent vous aider lors de la configuration des téléphones dans votre organisation.

> [!NOTE]
> Skype Entreprise sera progressivement remplacé par Microsoft Teams comme mode de communication principal dans Microsoft 365 et Office 365.  Pour plus d’informations, voir une nouvelle vision des communications intelligentes dans [Office 365.](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/)
>
>Pour obtenir les dernières mises à jour et les informations les plus récentes sur les appareils pris en charge, consultez les appareils Microsoft Teams pour [les communications intelligentes.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)
  
## <a name="supported-phones"></a>Téléphones pris en charge
  
Microsoft s’associe et travaille en étroite collaboration avec Polycom, Yealink et AudioCodes pour développer et certifier une grande variété d’appareils via le Partner IP Phone Program (PIP) pour le système téléphonique.
  
Lors de la commande de nouveaux téléphones pour Skype Entreprise, il est important d’acheter des téléphones avec *l’ID de produit qui leur est fourni.* Ces ID de produit vous assurent que la version de Skype Entreprise Online qualifiée sera installée sur les téléphones que vous recevez.
  
|Partenaire de téléphonie  |ID de produit propre à Skype Entreprise  |
|:-----|:-----|
|Polycom   |ID de produit -019   |
|Yealink   |SIP-TXXG Édition Skype Entreprise   |
|AudioCodes   |UCXXXHDEG (SfB)   |
   
Pour plus d’informations sur les téléphones Polycom, consultez [la bibliothèque de documentation Poly.](https://documents.polycom.com/category/voice)
  
Pour plus de détails sur les téléphones Yealink, reportez-vous à la page [Skype for Business IP Phones](http://www.yealink.com/products_list_10.html#filter2).
  
Pour plus d’informations sur les téléphones AudioCodes, consultez [les téléphones IP Skype Entreprise.](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)
  
> [!NOTE]
> Lync Phone Edition est pris en charge avec Skype Entreprise Online, mais pas avec Microsoft Teams. Le support standard de la plate-forme LPE a pris fin le 10 avril 2014, avec prise en charge étendue jusqu'au 11 avril 2023 pour s’aligner sur la politique de prise en charge de Lync Server 2013. Pour [plus d’informations](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) sur le cycle de vie de LPE, voir Cycle de vie des produits Microsoft. Les modèles CAP pour LPE ne sont pas pris en charge avec Skype Entreprise Online.
>
> Plus tard cette année, Office 365 ne prendra en charge aucune version de TLS antérieure à 1.2. Dans la mesure où le système d’exploitation sous-jacent de LPE ne prend pas en charge TLS 1.2, LPE ne sera plus prise en charge pour se connecter à Office 365. Pour plus d’informations, consultez [Préparation à l’utilisation obligatoire de TLS 1.2 dans Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Microprogramme pris en charge

Il s’agit de la version de logiciel minimale requise pour que les téléphones pris en charge fonctionnent avec Phone System :
  

|Type de téléphone |Microprogramme minimum |Date de publication |
|:-----|:-----|:-----|
|Optimisé (Lync Phone Edition)   |4.0.7577.4463   |Mai 2015   |
|Polycom VVX Series certifié   |5.4.0A   |Décembre 2015   |
|Yealink   |X.8.1.52   |Février 2017   |
|AudioCodes   |3.0.0.459.1   |Décembre 2016   |

Pour plus d’informations sur les versions de microprogramme certifiées actuelles, [consultez les téléphones IP Skype Entreprise.](../../../SfbPartnerCertification/certification/devices-ip-phones.md)

> [!NOTE]
> Les téléphones Lync Phone Edition (LPE) configurés pour votre déploiement local doivent être mis à jour avec la version minimale ou ultérieure du microprogramme avant la migration des utilisateurs vers Skype Entreprise Online. Si vous migrez vos utilisateurs du déploiement local vers Skype Entreprise Online avant de mettre à jour le microprogramme sur les téléphones, ces utilisateurs ne pourront pas se connecter à Skype Entreprise Online avec leurs téléphones. 
  
## <a name="required-licenses"></a>Licences requises

Skype Entreprise Online ne nécessite aucune licence Microsoft supplémentaire en plus des licences utilisateur. Pour en savoir plus sur les licences utilisateur requises, consultez la gestion des licences des modules [add-on dans Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)Entreprise et Microsoft Teams.
  
Les modèles de licence du fabricant peuvent varier entre le microprogramme certifié d’Open SIP et de Skype Entreprise. Si vous réaffectez un modèle certifié avec un microprogramme Open SIP, vous devrez vérifier les conditions de licences du microprogramme auprès du fabricant.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Ensemble des fonctionnalités de téléphones connectés Skype Entreprise Online

Pour obtenir l’ensemble des fonctionnalités et fonctionnalités de l’appareil, consultez le guide d’utilisation du fabricant.
  

|Fonctionnalité  |Polycom 3PIP  |Yealink 3PIP |AudioCodes 3PIP |LPE |
|:-----|:-----|:-----|:-----|:-----|
|Se connecter à l'aide des informations de connexion de l'utilisateur   |Oui  |Oui   |Oui   |Non   |
|Se connecter via un PC (couplage), Windows uniquement   |Oui   |Oui   |Oui   |Oui   |
|Se connecter à l'aide de (connexion Web)  <br/>  <br/> **Remarque :** Consultez la matrice de prise en charge dans le guide de déploiement.  |Oui   |Oui   |Oui   |Non   |
|Cliquez sur participer à une réunion   |Oui   |Oui   |Oui   |Oui   |
|Cliquer pour marquer un numéro (couplage)   |Oui   |Oui   |Oui   |Oui, > |
|Contrôles de réunion   |Oui   |Oui   |Oui   |Oui   |
|Messagerie vocale visuelle   |Oui   |Oui   |Oui   |Oui   |
|Verrouillage du téléphone   |Oui   |Oui   |Oui   |Oui   |
|Mise à jour de l'appareil   |Oui   |Oui   |Oui   |Oui   |
|Provisionnement intrabande   |Oui   |Oui   |Oui   |Oui   |
|QoE   |Oui   |Oui   |Oui   |Non  |
|Chargement de journaux  <br/> <br/> **Remarque :** Pour l’instant, tous les journaux sont téléchargés uniquement pour l’équipe de support technique Microsoft. l’accès client aux journaux téléphoniques n’est pas encore disponible.           |Oui   |Oui   |Oui   |Oui   |
|Authentification moderne   |Oui   |Oui   |Oui   |Non   |
|Numéros d'urgence multiples   |Oui   |Non   |Non   |Oui   |
|Intégration du calendrier Exchange*   |Oui   |Oui   |Oui   |Oui  <br/> <br/> **Remarque :** Nécessite un thering PC           |
|Intégration de la présence   |Oui   |Oui   |Oui   |Oui   |
|Annuaire d'entreprise   |Oui   |Oui   |Oui   |Oui   |
|Délégation   |Oui   |Oui   |Oui   |Non   |
|Intégration de l'image des contacts   |Non   |Oui  |Non   |Oui   |


     
> [!NOTE]
> CX 600 ou les autres téléphones Aries ne prennent pas en charge l’authentification multifacteur (MFA). Si vous forcez l'usage de l'option MFA, ces appareils échouent à vous connecter. Ces périphériques doivent utiliser des ID de l’Organisation uniquement pour l’authentification.
 
## <a name="what-else-should-you-know"></a>Informations supplémentaires
Pour obtenir des instructions de configuration détaillées, consultez la page [Déploiement de téléphones Skype Entreprise Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Rubriques connexes
[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Voici les avantages du système téléphonique](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
