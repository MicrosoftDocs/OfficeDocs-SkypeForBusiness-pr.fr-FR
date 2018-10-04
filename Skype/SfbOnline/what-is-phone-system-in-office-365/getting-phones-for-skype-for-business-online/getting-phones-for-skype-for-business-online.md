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
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez quels téléphones fonctionnent avec Skype Entreprise à partir de Polycom, HP et Mitel, ainsi que les licences requises. '
ms.openlocfilehash: 8b218161268855a1b89aa54fd0e40c4b308db40d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371564"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obtention de numéros de téléphone pour Skype Entreprise Online

Skype for Business Online qualifies and supports desktop phones for users who want to have a traditional phone experience, rather than use the Skype for Business app. This topic covers the phones and firmware versions that are supported for use in Skype for Business Online and other information that can help you when you are setting up phones in your organization.
  
Pour obtenir les dernières mises à jour et la plupart des informations à jour sur les appareils pris en charge, voir le [Skype pour le catalogue de périphérique Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Téléphones pris en charge

Pour Skype pour les utilisateurs professionnels en ligne, vous pouvez choisir parmi plusieurs modèles dans le *certifié pour Skype pour les téléphones d’entreprise* et téléphones exécutant Lync Phone Edition (LPE) répertoriées sous la Skype pour la catégorie Business Online dans le [Skype pour appareil d’entreprise Catalogue](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
Microsoft est un partenariat et en étroite collaboration avec Polycom, Yealink et AudioCodes pour développer et certifiez un large éventail d’appareils via le programme de téléphone IP (PIP) partenaire pour le système téléphonique dans Office 365 et Skype pour Business Server.
  
When ordering new phones for Skype for Business, it is important to buy phones with the *right product ID*. These product IDs will ensure that the phones you receive have the Skype for Business Online qualified version already installed.
  
|||
|:-----|:-----|
|**Partenaire de téléphonie** <br/> |**ID de produit propre à Skype Entreprise** <br/> |
|Polycom  <br/> |ID de produit -019  <br/> |
|Yealink  <br/> |SIP-TXXG Édition Skype Entreprise  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Pour plus de détails sur les téléphones Polycom, reportez-vous à la page [Voice Solutions for Microsoft](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
  
Pour plus de détails sur les téléphones Yealink, reportez-vous à la page [Skype for Business IP Phones](http://www.yealink.com/products_list_10.html#filter2).
  
Pour plus d’informations sur les téléphones AudioCodes, voir [Skype pour les téléphones IP Business](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition is supported with Skype for Business Online, but not with Microsoft Teams. Mainstream support for the LPE platform ended by April/10/2014, with extended support until April/11/2023 to align with the product support lifecycle of Lync Server 2013. See [Microsoft Product Lifecycle](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) for details on the LPE lifecycle. LPE CAP models aren't supported with Skype for Business Online.
>
> Later this year, Office 365 will not support any version of TLS older than 1.2. Since the underlying operating system of LPE does not support TLS 1.2, LPE will not be supported to connect to Office 365 anymore. See [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365) for more information.
  
## <a name="supported-firmware"></a>Microprogramme pris en charge

Il s’agit de la version logicielle minimale requise pour les téléphones pris en charge pour fonctionner avec le système téléphonique dans Office 365 :
  
||||
|:-----|:-----|:-----|
|**Type de téléphone** <br/> |**Microprogramme minimum** <br/> |**Date de publication** <br/> |
|Optimisé (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Mai 2015  <br/> |
|Polycom VVX Series certifié  <br/> |5.4.0A  <br/> |Décembre 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Février 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Décembre 2016  <br/> |
   
> [!NOTE]
> Les téléphones Lync Phone Edition (LPE) configurés pour votre déploiement local doivent être mis à jour avec la version minimale ou ultérieure du microprogramme avant la migration des utilisateurs vers Skype Entreprise Online. Si vous migrez vos utilisateurs du déploiement local vers Skype Entreprise Online avant de mettre à jour le microprogramme sur les téléphones, ces utilisateurs ne pourront pas se connecter à Skype Entreprise Online avec leurs téléphones. 
  
## <a name="required-licenses"></a>Licences requises

Skype for Business Online doesn't require any additional Microsoft license other than the user licenses. To learn more about the required user licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Manufacturer licensing models might vary between open SIP and Skype for Business Certified firmware. If you are repurposing a certified model with an Open SIP firmware, you will need to verify firmware license requirements with the manufacturer.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype pour le jeu de fonctionnalités Business Online connecté téléphones

Pour périphérique complet des fonctionnalités, consultez les guides du fabricant.
  
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
|Chargement de journaux  <br/> <br/> **Remarque :** Actuellement, tous les journaux sont téléchargés vers l’équipe de Support Microsoft uniquement ; client l’accès aux journaux d’appels téléphoniques ne sont pas encore disponibles.           |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Authentification moderne  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Numéros d'urgence multiples  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |Oui  <br/> |
|Intégration du calendrier Exchange*  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> <br/> **Remarque :** Requiert l’attache de PC           |
|Intégration de la présence  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Annuaire d'entreprise  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|Délégation  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Intégration de l'image des contacts  <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |Oui  <br/> |
||||||

     
> [!NOTE]
> CX 600 or any other Aries phones don't support multifactor authentication (MFA). If you force MFA, these devices will fail to sign-in. These devices must use only Org ID for authetication.
 
## <a name="what-else-should-you-know"></a>Informations supplémentaires
Pour obtenir des instructions de configuration détaillées, consultez la page [Déploiement de téléphones Skype Entreprise Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Rubriques connexes
[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](../getting-service-phone-numbers.md)

[Voici les avantages du système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 