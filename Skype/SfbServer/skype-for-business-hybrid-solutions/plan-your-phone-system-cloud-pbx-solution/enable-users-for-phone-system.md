---
title: Activation des utilisateurs pour le système téléphonique avec une connectivité PSTN en local dans Skype Entreprise Server
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
description: Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique avec une connectivité RTC locale. Avant de suivre la procédure décrite dans cette rubrique, vous devez lire les rubriques suivantes :.
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359140"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Activation des utilisateurs pour le système téléphonique avec une connectivité PSTN en local dans Skype Entreprise Server

Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique avec une connectivité RTC locale. Avant de suivre la procédure décrite dans cette rubrique, vous devez lire les rubriques suivantes :.
  
- Pour en savoir plus sur la configuration de la connectivité hybride, reportez-vous à la rubrique [plan Hybrid Connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et [déployer une connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Pour en savoir plus sur la planification de votre déploiement, reportez-vous à la rubrique [plan Phone System with on-premises Connectivity Connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Pour en savoir plus sur le système téléphonique, y compris sur les licences et les plans, voir [RTC Calling forfaits for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
> [!Important]
> Skype entreprise Online sera supprimé le 31 juillet 2021 après lequel le service ne sera plus accessible.  De plus, la connectivité PSTN entre votre environnement local, que ce soit via Skype entreprise Server ou Cloud Connector Edition et Skype entreprise Online, ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Déplacement des utilisateurs vers le système téléphonique avec une connectivité RTC locale

Avant de déplacer vos utilisateurs vers Skype entreprise Online, il est recommandé d’activer les utilisateurs locaux dans Skype entreprise Server ou Lync Server 2013, puis de les déplacer en ligne. Pour plus d’informations, reportez-vous à la section planification de la [connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et à la section Considérations spéciales de [activer les utilisateurs pour voix entreprise sur site](enable-the-users-for-enterprise-voice-on-premises.md) (effectué lorsque les utilisateurs sont hébergés en local). 
  
Tous les utilisateurs doivent être créés dans Active Directory en local et synchronisés avec Microsoft 365 ou Office 365 à l’aide de la version prise en charge d’Azure AD Connector. Vous ne pouvez pas activer les utilisateurs pour le système téléphonique dans Office 365 qui ont été créés directement dans Azure AD. Si vous souhaitez activer le système téléphonique avec une connectivité RTC locale pour un utilisateur qui a été créé dans Azure AD, vous devez créer un nouveau compte pour cet utilisateur dans votre annuaire Active Directory local, configurer le compte local, puis synchroniser le compte à l’aide d’une version prise en charge de l’outil Azure AD Connector. 
  
L’activation d’un utilisateur pour le système téléphonique avec une connectivité RTC locale, puis son déplacement vers Skype entreprise Online nécessite les étapes suivantes :
  
- [Activer les utilisateurs pour voix entreprise sur site](enable-the-users-for-enterprise-voice-on-premises.md) (effectué lorsque les utilisateurs sont hébergés en local).
    
- [Affecter une stratégie de routage des communications vocales](assign-a-voice-routing-policy.md) (effectuée pendant que les utilisateurs sont hébergés en local).
    
- [Synchroniser les utilisateurs avec le Cloud et attribuer des licences](synchronize-users-to-the-cloud-and-assign-licenses.md) (effectué à l’aide d’Office 365).
    
- [Déplacez les utilisateurs locaux vers Skype entreprise Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (effectué à l’aide de Windows PowerShell en local, mais à l’aide de vos informations d’identification d’administrateur Office 365).
    
- [Activer les utilisateurs pour voix entreprise Online et messagerie vocale du système téléphonique](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (effectué à l’aide de PowerShell à distance.
    

