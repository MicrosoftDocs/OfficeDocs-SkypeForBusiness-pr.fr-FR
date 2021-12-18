---
title: Activation des utilisateurs pour le Système téléphonique avec une connectivité PSTN en local dans Skype Entreprise Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'Cette rubrique décrit comment activer les utilisateurs pour Système téléphonique avec une connectivité PSTN sur site. Avant de suivre les étapes de cette rubrique, vous devez lire les rubriques suivantes :'
ms.openlocfilehash: ffd7e9f02466dddeef31ba7ffd3a194a04b9b2ff
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563661"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Activation des utilisateurs pour le Système téléphonique avec une connectivité PSTN en local dans Skype Entreprise Server

Cette rubrique décrit comment activer les utilisateurs pour Système téléphonique avec une connectivité PSTN sur site. Avant de suivre les étapes de cette rubrique, vous devez lire les rubriques suivantes :
  
- Pour découvrir comment configurer la connectivité hybride, voir Planifier la connectivité hybride entre Skype Entreprise Server et [Skype Entreprise Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) et déployer la connectivité hybride entre Skype Entreprise Server et Skype Entreprise [Online.](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
    
- Pour en savoir plus sur la planification de votre déploiement, voir Plan Système téléphonique avec la connectivité [PSTN](plan-phone-system-with-on-premises-pstn-connectivity.md)sur site dans Skype Entreprise Server .
    
- Pour en savoir plus sur les Système téléphonique, notamment les licences et les plans, consultez les [plans d’appel PSTN Skype Entreprise](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
> [!Important]
> Skype Entreprise Online a été retiré le 31 juillet 2021 et la connectivité PSTN entre votre environnement local, que ce soit via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online, n’est plus prise en charge. Découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Déplacement d’utilisateurs Système téléphonique avec une connectivité PSTN sur site

Avant de déplacer vos utilisateurs vers Skype Entreprise Online, il est recommandé d’activer vos utilisateurs en local dans Skype Entreprise Server ou Lync Server 2013, puis de les déplacer en ligne. Pour plus d’informations, voir [Plan hybrid connectivity between Skype Entreprise Server and Skype Entreprise Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and the special considerations section of Enable the users for Voix Entreprise on [premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises). 
  
Tous les utilisateurs doivent être créés dans Active Directory en local et synchronisés avec Microsoft 365 ou Office 365 à l’aide de la version prise en charge de Azure AD Connector. Vous ne pouvez pas activer les utilisateurs Système téléphonique dans Office 365 qui ont été créés directement dans Azure AD. Si vous souhaitez activer Système téléphonique avec une connectivité PSTN sur site pour un utilisateur qui a été créé dans Azure AD, vous devez créer un compte pour cet utilisateur dans votre AD local, configurer le compte local, puis synchroniser le compte à l’aide d’une version prise en charge de l’outil connecteur Azure AD. 
  
L’activation d’un Système téléphonique avec une connectivité PSTN sur site, puis son déplacement vers Skype Entreprise Online nécessite les étapes suivantes :
  
- [Activez les utilisateurs pour Voix Entreprise sur site](enable-the-users-for-enterprise-voice-on-premises.md) (effectuée lorsque les utilisateurs sont locaux).
    
- [Affecter une stratégie de routage des](assign-a-voice-routing-policy.md) voix (effectuée lorsque les utilisateurs sont en local).
    
- [Synchroniser les utilisateurs avec le cloud et attribuer des licences](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (effectuées à l’aide de Office 365).
    
- [Déplacez les utilisateurs](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) locaux vers Skype Entreprise Online (effectué à l’aide Windows PowerShell en local, mais à l’aide de vos informations d Office 365'administrateur).
    
- [Activez les utilisateurs pour Voix Entreprise en ligne et Système téléphonique messagerie](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) vocale (effectuée à l’aide de Remote PowerShell.
