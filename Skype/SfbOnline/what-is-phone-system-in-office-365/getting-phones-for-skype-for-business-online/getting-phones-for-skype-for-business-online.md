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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez quels téléphones fonctionnent avec Skype Entreprise à partir de Polycom, HP et Mitel, ainsi que les licences requises. '
ms.openlocfilehash: 441effac4256ee01f713e10e592ea3402726d5f3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863762"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obtention de téléphone pour Skype Entreprise Online

Skype Entreprise Online qualifie et prend en charge des téléphones de bureau pour les utilisateurs qui souhaitent avoir une expérience téléphonique traditionnelle, plutôt que d’utiliser l'application Skype Entreprise. Cette rubrique porte sur les téléphones et les versions de microprogramme pris en charge avec Skype Entreprise Online et d'autres informations utiles pour la configuration des téléphones dans votre organisation.
  
Pour obtenir les dernières mises à jour et informations récentes sur les appareils pris en charge, consultez le catalogue [Appareils Skype Entreprise](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Téléphones pris en charge

Pour les utilisateurs de Skype Entreprise Online, vous pouvez choisir différents modèles parmi les  *Téléphones certifiés pour Skype Entreprise*et les téléphones Lync Phone Edition (LPE) répertoriés sous la catégorie Skype Entreprise Online du catalogue[Appareils Skype Entreprise](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
Microsoft est en partenariat et en étroite collaboration avec Polycom, Yealink et AudioCodes pour développer et certifier un large éventail d’appareils via le programme de téléphone IP (PIP) partenaire pour le système téléphonique dans Office 365 et Skype Entreprise Server.
  
Lorsque vous commandez un nouveau téléphone pour Skype Entreprise, il est important de sélectionner l' *ID de produit adéquat*. Cet ID permet de garantir que la version de Skype Entreprise Online qualifiée sera installée sur le téléphone commandé.
  
|||
|:-----|:-----|
|**Partenaire de téléphonie** <br/> |**ID de produit propre à Skype Entreprise** <br/> |
|Polycom  <br/> |ID de produit -019  <br/> |
|Yealink  <br/> |SIP-TXXG Édition Skype Entreprise  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Pour plus de détails sur les téléphones Polycom, reportez-vous à la page [Voice Solutions for Microsoft](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
  
Pour plus de détails sur les téléphones Yealink, reportez-vous à la page [Skype for Business IP Phones](http://www.yealink.com/products_list_10.html#filter2).
  
Pour plus de détails sur les téléphones AudioCodes, reportez-vous à la page [Téléphones IP Skype Entreprise](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition est pris en charge avec Skype Entreprise Online, mais pas avec Microsoft Teams. Le support standard de la plate-forme LPE a pris fin le 10 avril 2014, avec prise en charge étendue jusqu'au 11 avril 2023 pour s’aligner sur la politique de prise en charge de Lync Server 2013. Pour plus de détails sur le cycle de vie LPE, reportez-vous à la page [Cycle de vie des produits Microsoft](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO). Les modèles CAP pour LPE ne sont pas pris en charge avec Skype Entreprise Online.
>
> Dans le courant de l'année, Office 365 ne prendra pas en charge les versions de TLS antérieures à 1.2. Dans la mesure où le système d’exploitation sous-jacent de LPE ne prend pas en charge TLS 1.2, LPE ne sera plus prise en charge pour se connecter à Office 365. Pour plus d’informations, consultez [Préparation à l’utilisation obligatoire de TLS 1.2 dans Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Microprogrammes pris en charge

Il s’agit de la version logicielle minimale requise pour les téléphones pris en charge pour fonctionner avec le système téléphonique dans Office 365 :
  
||||
|:-----|:-----|:-----|
|**Type de téléphone** <br/> |**Microprogramme minimum** <br/> |**Date de sortie** <br/> |
|Optimisé (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Mai 2015  <br/> |
|Polycom VVX Series certifié  <br/> |5.4.0A  <br/> |Décembre 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Février 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Décembre 2016  <br/> |
   
> [!NOTE]
Les téléphones Lync Phone Edition (LPE) configurés pour votre déploiement local doivent être mis à jour avec la version minimale ou ultérieure du microprogramme avant la migration des utilisateurs vers Skype Entreprise Online. Si vous migrez vos utilisateurs du déploiement local vers Skype Entreprise Online avant de mettre à jour le microprogramme sur les téléphones, ces utilisateurs ne pourront pas se connecter à Skype Entreprise Online avec leurs téléphones. 
  
## <a name="required-licenses"></a>Licences requises

Les téléphones Skype Entreprise Online ne nécessitent aucune licence Microsoft supplémentaire en dehors des licences utilisateur. Pour en savoir plus sur les licences utilisateur requises, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Les modèles de licence du fabricant pour les microprogrammes open SIP et Skype Entreprise peuvent être différents. Si vous réaffectez un modèle certifié avec un microprogramme Open SIP, vous devrez vérifier les conditions de licences du microprogramme auprès du fabricant.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Ensemble des fonctionnalités pour téléphones connectés Skype Entreprise Online

Pour en savoir plus sur les fonctionnalités et fonctions complètes de votre appareil, consultez le guide d'utilisation du fabricant.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Fonctionnalité** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|Se connecter à l'aide des informations de connexion de l'utilisateur  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Se connecter via un PC (couplage), Windows uniquement  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Se connecter à l'aide de (connexion Web)  <br/>  <br/> **Remarque :** Consultez la matrice de prise en charge dans le guide de déploiement.           |Oui  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Cliquez sur participer à une réunion  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Cliquer pour marquer un numéro (couplage)  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Contrôles de réunion  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Messagerie vocale visuelle  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Verrouillage du téléphone  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Mise à jour de l'appareil  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Provisionnement intrabande  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|QoE  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Téléchargement de journaux  <br/> <br/> **Remarque :** Actuellement, tous les journaux sont chargés pour l'équipe de support technique de Microsoft uniquement, l'accès client aux journaux des téléphones n'est pas encore disponible.           |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Authentification moderne  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Numéros d'urgence multiples  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |Oui  <br/> |
|Intégration du calendrier Exchange*  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> <br/> **Remarque :** Requiert la connexion au PC           |
|Intégration de la présence  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Annuaire d'entreprise  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Délégation  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Intégration de l'image des contacts  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |Oui  <br/> |
||||||

     
> [!NOTE]
> CX 600 ou les autres téléphones Aries ne prennent pas en charge l’authentification multifacteur (MFA). Si vous forcez l'usage de l'option MFA, ces appareils échouent à vous connecter. Ces périphériques doivent utiliser des ID de l’Organisation uniquement pour l’authentification.
 
## <a name="what-else-should-you-know"></a>Informations supplémentaires
Pour obtenir des instructions de configuration détaillées, consultez la page [Déploiement de téléphones Skype Entreprise Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Rubriques connexes
[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](../getting-service-phone-numbers.md)

[Voici les avantages du système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilité des forfaits d'appels et d'audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 