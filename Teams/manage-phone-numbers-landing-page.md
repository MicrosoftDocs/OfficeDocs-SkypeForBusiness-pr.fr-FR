---
title: Gérer les numéros de téléphone de votre organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jenstr
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: Découvrez comment obtenir et gérer les numéros de téléphone utilisateur (abonné) et de service (gratuits et gratuits) pour Microsoft Teams pour votre organisation.
ms.openlocfilehash: 613a3f5f287615c6e18024d1afba1d94d0fea67c
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606743"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>Gérer les numéros de téléphone de votre organisation

Actuellement, Microsoft prend en charge deux types de numéros de téléphone : 

- [**Les numéros d’utilisateur**](#user-telephone-numbers), également appelés numéros d’abonnés, qui peuvent être affectés aux utilisateurs de votre organisation.

- [**Numéros de service**](#service-telephone-numbers), qui sont affectés à des services, tels que l’audioconférence, [les standards automatiques](plan-auto-attendant-call-queue.md) ou [les files d’attente d’appels](plan-auto-attendant-call-queue.md).[](deploy-audio-conferencing-teams-landing-page.md)

Microsoft s’efforce de simplifier les types de nombres, mais pour l’instant, vous devez décider :

- Quels sont les emplacements d’utilisateur qui ont besoin de nouveaux numéros de téléphone de Microsoft ?
- De quel type de numéro de téléphone (abonné ou service) ai-je besoin ?
- Comment faire les numéros de téléphone existants vers Teams ?

La façon dont vous acquérez et gérez des numéros de téléphone diffère en fonction de votre option de connectivité rtc (RTC).

- Pour plus d’informations sur la gestion des numéros de téléphone pour le plan d’appels Microsoft, consultez [Gérer les numéros de téléphone pour les forfaits d’appels](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Pour plus d’informations sur la gestion des numéros de téléphone pour Operator Connect, consultez [Configurer des numéros de téléphone avec Operator Connect](operator-connect-configure.md#set-up-phone-numbers).

- Pour plus d’informations sur la gestion des numéros de téléphone pour Fournisseur de connectivité mobile (préversion publique), consultez [Configurer les numéros de téléphone avec Fournisseur de connectivité mobile](operator-connect-mobile-configure.md#set-up-phone-numbers).

- Pour plus d’informations sur la gestion des numéros de téléphone pour le routage direct, consultez [Configurer le numéro de téléphone et activer la voix d’entreprise](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).




> [!NOTE]
> Si vous avez besoin de types de numéros supplémentaires ou autres que ceux affichés dans le Centre d’administration Microsoft Teams, vous pouvez envoyer une demande de numéro de téléphone au [Centre de services de numéro](https://pstnsd.powerappsportals.com/) de téléphone.

## <a name="user-telephone-numbers"></a>Numéros de téléphone de l’utilisateur

Il existe deux types de numéros de téléphone d’utilisateur, qui peuvent être attribués aux utilisateurs de votre organisation :  
    
- **Les nombres géographiques** ont une relation avec une zone géographique et sont les plus courants. Par exemple, dans la plupart des cas, les numéros de téléphone géographiques ne peuvent être utilisés qu’au sein d’une adresse, d’une ville, d’un état ou d’une région donnée du pays.
    
- **Les nombres non géographiques** sont appelés nombres nationaux ou parfois numéros VoIP. Ces nombres n’ont pas de relation avec une zone géographique au sein d’un pays ou d’une région. Par exemple, les numéros non géographiques ont souvent le même coût lors de l’appel du numéro à partir de n’importe où dans le pays/la région. En outre, certains pays, comme le Danemark, n’ont que des numéros non géographiques disponibles.


## <a name="service-telephone-numbers"></a>Numéros de téléphone de service  

Cette section décrit les numéros de service disponibles auprès de Microsoft qui sont inclus dans vos licences. Pour plus d’informations sur les numéros de service fournis par Operator Connect ou le routage direct, contactez votre fournisseur. 

Il existe deux types de numéros de téléphone de service fournis par Microsoft : payant et gratuit, qui peuvent être affectés à des services tels que l’audioconférence, les standards automatiques ou les files d’attente d’appels. Les numéros de service ont une capacité d’appel simultanée supérieure à celle des numéros d’utilisateur. La disponibilité des numéros de service varie selon le pays/la région et le type de numéro (qu’il s’agisse d’un numéro payant ou gratuit). Les licences de téléphonie de Microsoft dans chaque pays/région déterminent à quoi le nombre peut être utilisé.
    
 - **Numéros de service payants** : il existe deux types de numéros de service payants, ce qui peut entraîner un coût de péage pour l’appelant :
    
   - **Nombres géographiques** Les nombres géographiques ont une relation avec une zone géographique. Par exemple, dans la plupart des cas, les numéros de téléphone géographiques ne peuvent être utilisés qu’au sein d’une adresse, d’une ville, d’un état ou d’une région donnée du pays.
        
   - **Nombres non géographiques** Les nombres non géographiques sont des nombres nationaux qui n’ont pas de relation avec une zone géographique au sein d’un pays ou d’une région. Par exemple, les numéros non géographiques ont souvent le même coût lors de l’appel du numéro à partir de n’importe où dans le pays/la région.
   
- **Numéros de service gratuits** : ces numéros de service n’entraînent généralement pas de frais de péage pour l’appelant. Teams fournit des numéros gratuits nationaux dans plus de 60 pays/régions.
    
    > [!CAUTION]
    > Certains pays/régions et les types de numéros d’origine, tels que les appels provenant de téléphones mobiles, peuvent, dans certains cas, entraîner un coût de péage pour l’appelant. 

## <a name="where-phone-numbers-are-managed"></a>Où les numéros de téléphone sont gérés

L’emplacement et la façon dont les nombres sont gérés dépendent de l’option de connectivité RTC :

- Les numéros de téléphone microsoft Calling Plan et Operator Connect ne peuvent être gérés que dans Microsoft 365.

- Les numéros de téléphone de routage direct peuvent être gérés dans le Active Directory local ou dans Microsoft 365, comme décrit dans les sections suivantes.

### <a name="direct-routing-numbers-managed-in-an-on-premises-active-directory"></a>Numéros de routage direct gérés dans un Active Directory local

Si vous avez ou avez eu un déploiement hybride Skype Entreprise Server, votre Active Directory local est probablement synchronisée avec Microsoft 365. Cela signifie que les attributs d’annuaire sur les comptes d’utilisateurs et de ressources sont gérés dans le Active Directory local et synchronisés dans Microsoft 365.

Si le numéro de téléphone de routage direct est géré sur le compte d’utilisateur ou de ressource dans le Active Directory local, le paramètre msRTCSIP-Line sur le compte contient une valeur. Vous pouvez utiliser un outil tel que ADSI Edit pour afficher le paramètre msRTCSIP-Line pour un compte d’utilisateur ou de ressource auquel un numéro de téléphone de routage direct est affecté dans Active Directory local.   

Une fois ce paramètre synchronisé automatiquement avec le compte d’utilisateur ou de ressource dans Microsoft 365 via le processus de synchronisation d’annuaires (Azure AD Connect), vous pouvez afficher le numéro de téléphone en examinant le paramètre OnPremLineURi dans la sortie de l’applet de commande [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) .

| Où | Paramètre | Valeur |
| :------------| :-------| :---------|
| AD local | msRTCSIP-Line | tel:+14255551234 |
| Microsoft 365 | OnPremLineURi | tel:+14255551234 |

### <a name="direct-routing-numbers-managed-in-microsoft-365"></a>Numéros de routage direct gérés dans Microsoft 365

Si vous ne gérez pas les numéros de téléphone de routage direct dans le Active Directory local, ils sont gérés dans Microsoft 365. Étant donné que les numéros de téléphone ne sont pas synchronisés avec Microsoft 365, ils ne sont pas visibles dans le paramètre OnPremLineUri dans la sortie de l’exécution de l’applet de commande Get-CsOnlineUser pour l’utilisateur ou le compte de ressource.

### <a name="direct-routing-numbers-managed-in-both-an-on-premises-active-directory-and-microsoft-365"></a>Numéros de routage direct gérés dans un Active Directory local et Microsoft 365

Il est possible de gérer les numéros de téléphone de routage direct de certains comptes d’utilisateurs et de ressources dans un Active Directory local et des numéros de téléphone de routage direct d’autres comptes dans Microsoft 365. Cette fonctionnalité varie selon que l’attribut msRTCSIP-Line est défini sur le compte d’utilisateur ou de ressource dans le Active Directory local.    

### <a name="change-where-direct-routing-phone-numbers-are-managed"></a>Modifier l’emplacement de gestion des numéros de téléphone de routage direct

Pour modifier l’emplacement de gestion d’un numéro de téléphone de routage direct, vous devez supprimer le numéro de téléphone de l’attribut msRTCSIP-Line sur l’utilisateur ou resoucer le compte dans le Active Directory local.   

Pour plus d’informations, consultez [Effacer les attributs Skype Entreprise pour tous les utilisateurs locaux dans Active Directory](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory.md). Notez que le numéro de téléphone doit être réaffecté au compte d’utilisateur ou de ressource dans Microsoft 365.

Une fois la suppression synchronisée avec Microsoft 365, l’attribut OnPremLineUri dans la sortie de Get-CsOnlineUser sur le compte d’utilisateur ou de ressource est vide. 

