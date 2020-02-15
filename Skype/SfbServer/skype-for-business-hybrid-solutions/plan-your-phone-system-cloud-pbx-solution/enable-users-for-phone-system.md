---
title: Activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité RTC locale dans Skype entreprise Server
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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité RTC locale. Avant de suivre la procédure décrite dans cette rubrique, vous devez lire les rubriques suivantes :.
ms.openlocfilehash: 87dcafcfe0c5ce69bcdbcd9809d23cea80c234ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050186"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité RTC locale dans Skype entreprise Server
 
Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité RTC locale. Avant de suivre la procédure décrite dans cette rubrique, vous devez lire les rubriques suivantes :.
  
- Pour en savoir plus sur la configuration de la connectivité hybride, reportez-vous à la rubrique [plan Hybrid Connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et [déployer une connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Pour en savoir plus sur la planification de votre déploiement, reportez-vous à [plan Phone System in Office 365 with local RTC Connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Pour en savoir plus sur le système téléphonique dans Office 365, y compris les licences et les plans, voir [RTC Calling forfaits for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Déplacement d’utilisateurs vers le système téléphonique dans Office 365 avec une connectivité RTC locale

Avant de déplacer vos utilisateurs vers Skype entreprise Online, il est recommandé d’activer les utilisateurs locaux dans Skype entreprise Server ou Lync Server 2013, puis de les déplacer en ligne. Pour plus d’informations, reportez-vous à la section planification de la [connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et à la section Considérations spéciales de [activer les utilisateurs pour voix entreprise sur site](enable-the-users-for-enterprise-voice-on-premises.md) (effectué lorsque les utilisateurs sont hébergés en local). 
  
Tous les utilisateurs doivent être créés dans Active Directory en local et synchronisés avec Office 365 à l’aide de la version prise en charge d’Azure AD Connector. Vous ne pouvez pas activer les utilisateurs pour le système téléphonique dans Office 365 qui ont été créés directement dans Azure AD. Si vous souhaitez activer le système téléphonique dans Office 365 avec une connectivité RTC locale pour un utilisateur qui a été créé dans Azure AD, vous devez créer un nouveau compte pour cet utilisateur dans votre annuaire Active Directory local, configurer le compte en local, puis synchroniser le compte à l’aide de une version prise en charge de l’outil Azure AD Connector. 
  
L’activation d’un utilisateur pour le système téléphonique dans Office 365 avec une connectivité RTC locale, puis son déplacement vers Skype entreprise Online nécessite les étapes suivantes :
  
- [Activer les utilisateurs pour voix entreprise sur site](enable-the-users-for-enterprise-voice-on-premises.md) (effectué lorsque les utilisateurs sont hébergés en local).
    
- [Affecter une stratégie de routage des communications vocales](assign-a-voice-routing-policy.md) (effectuée pendant que les utilisateurs sont hébergés en local).
    
- [Synchroniser les utilisateurs avec le Cloud et attribuer des licences](synchronize-users-to-the-cloud-and-assign-licenses.md) (effectué à l’aide d’Office 365).
    
- [Déplacez les utilisateurs locaux vers Skype entreprise Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (effectué à l’aide de Windows PowerShell en local, mais à l’aide de vos informations d’identification d’administrateur Office 365).
    
- [Activer les utilisateurs pour voix entreprise Online et le système téléphonique dans Office 365 la messagerie vocale](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (effectuée à l’aide de PowerShell à distance.
    

