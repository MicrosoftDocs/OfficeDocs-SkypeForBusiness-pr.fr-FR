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
description: 'Learn which phones work with Skype for Business from Polycom, HP, and Mitel, and the required licenses. '
ms.openlocfilehash: f12952944c85c77778a018de0f4f4b2bd39945b0
ms.sourcegitcommit: 4660539cf0a6f7fde5de0a68bc4866089962ce80
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2018
ms.locfileid: "22101963"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obtention de numéros de téléphone pour Skype Entreprise Online

Skype pour Business Online qualifiant et prend en charge des téléphones de bureau pour les utilisateurs qui souhaitent avoir une expérience traditionnels, plutôt que d’utiliser le Skype pour l’application de gestion. Cette rubrique couvre les téléphones et les versions de microprogramme pris en charge pour une utilisation dans Skype pour Business en ligne et d’autres informations qui peuvent vous aider à lorsque vous configurez les téléphones dans votre organisation.
  
Pour obtenir les dernières mises à jour et la plupart des informations à jour sur les appareils pris en charge, voir le [Skype pour le catalogue de périphérique Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Téléphones pris en charge

Pour Skype pour les utilisateurs professionnels en ligne, vous pouvez choisir parmi plusieurs modèles dans le *certifié pour Skype pour les téléphones d’entreprise* et téléphones exécutant Lync Phone Edition (LPE) répertoriées sous la Skype pour la catégorie Business Online dans le [Skype pour appareil d’entreprise Catalogue](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
Microsoft est un partenariat et en étroite collaboration avec Polycom, Yealink et AudioCodes pour développer et certifiez un large éventail d’appareils via le programme de téléphone IP (PIP) partenaire pour le système téléphonique dans Office 365 et Skype pour Business Server.
  
Lors de la commande nouveaux téléphones pour Skype pour les entreprises, il est important de téléphones dotés de l' *ID de produit de droite*. Ces ID de produit permet de garantir que les téléphones que vous recevez ont le Skype pour Business Online version complet est déjà installée.
  
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
> Lync Phone Edition est pris en charge avec Skype pour Business Online, mais pas avec Microsoft Teams. Le support standard de la plateforme LPE s’est terminée en avril/10/2014, avec prise en charge étendue jusqu'à avril/11/2023 pour s’aligner sur la politique de support de Lync Server 2013. Pour plus d’informations sur le cycle de vie LPE, voir [Politique de support Microsoft](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) . Les modèles CAP pour LPE ne sont pas pris en charge avec Skype Entreprise Online.
>
> Année, Office 365 ne prendra pas en charge toutes les versions d’antérieures à 1.2 TLS. Dans la mesure où le système d’exploitation sous-jacent de LPE ne prend pas en charge TLS 1.2, LPE ne sera pas prise en charge pour se connecter à Office 365 plus. Pour plus d’informations, consultez [préparation l’utilisation obligatoire de TLS 1.2 dans Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365) .
  
## <a name="supported-firmware"></a>Microprogramme pris en charge

Il s’agit de la version logicielle minimale requise pour les téléphones pris en charge fonctionner avec le système téléphonique dans Office 365 :
  
||||
|:-----|:-----|:-----|
|**Type de téléphone** <br/> |**Microprogramme minimum** <br/> |**Date de publication** <br/> |
|Optimisé (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Mai 2015  <br/> |
|Polycom VVX Series certifié  <br/> |5.4.0A  <br/> |Décembre 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Février 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Décembre 2016  <br/> |
   
> [!NOTE]
Les téléphones Lync Phone Edition (LPE) configurés pour votre déploiement local doivent être mis à jour avec la version minimale ou ultérieure du microprogramme avant la migration des utilisateurs vers Skype Entreprise Online. Si vous migrez vos utilisateurs du déploiement local vers Skype Entreprise Online avant de mettre à jour le microprogramme sur les téléphones, ces utilisateurs ne pourront pas se connecter à Skype Entreprise Online avec leurs téléphones. 
  
## <a name="required-licenses"></a>Licences requises

Skype pour Business Online ne requiert aucune licence Microsoft supplémentaire autres que les licences utilisateur. Pour en savoir plus sur les licences d’utilisateurs requis, voir [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Le fabricant de modèles de gestion des licences peut varier entre open SIP et Skype pour microprogramme Business certifié. Si vous réaffectez un modèle certifié avec un microprogramme Open SIP, vous devrez vérifier les conditions de licences du microprogramme auprès du fabricant.
  
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
> CX 600 ou les autres téléphones Aries ne prend en charge l’authentification multifacteur (MFA). Si vous forcez MFA, ces appareils échoue pour vous connecter. Ces périphériques doivent utiliser des ID d’organisation uniquement pour l’authentification.
 
## <a name="what-else-should-you-know"></a>Informations supplémentaires
Pour obtenir des instructions de configuration détaillées, consultez la page [Déploiement de téléphones Skype Entreprise Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Rubriques connexes
[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](../getting-service-phone-numbers.md)

[Voici les avantages du système téléphonique dans Office 365](../here-s-what-you-get-with-phone-system.md)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 