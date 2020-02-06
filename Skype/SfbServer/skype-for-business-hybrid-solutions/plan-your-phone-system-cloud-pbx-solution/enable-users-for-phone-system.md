---
title: Activer les utilisateurs pour le système téléphonique dans Office 365 avec la connectivité PSTN locale dans Skype entreprise Server
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
description: Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique dans Office 365 avec la connectivité PSTN locale. Avant de suivre les étapes décrites dans cette rubrique, vous devez lire ce qui suit :.
ms.openlocfilehash: c0c9f840c15e40aa3a78b69a5cbbf2f721251bbb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802184"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Activer les utilisateurs pour le système téléphonique dans Office 365 avec la connectivité PSTN locale dans Skype entreprise Server
 
Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique dans Office 365 avec la connectivité PSTN locale. Avant de suivre les étapes décrites dans cette rubrique, vous devez lire ce qui suit :.
  
- Pour plus d’informations sur la configuration d’une connectivité hybride, voir [planifier une connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et [déployer une connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Pour plus d’informations sur la planification de votre déploiement, reportez-vous à la rubrique [planification de système téléphonique dans Office 365 avec la connectivité PSTN locale dans Skype entreprise Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Pour en savoir plus sur le système téléphonique dans Office 365, y compris les licences et les offres, voir [forfaits d’appels RTC pour Skype entreprise](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Déplacement d’utilisateurs vers le système téléphonique dans Office 365 avec la connectivité PSTN locale

Avant de transférer vos utilisateurs dans Skype entreprise Online, nous vous recommandons d’activer les utilisateurs locaux dans Skype entreprise Server ou Lync Server 2013, puis de les déplacer en ligne. Pour plus d’informations, reportez-vous à la section [planifier une connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et la section Considérations spéciales de [l’activation de l’accès des utilisateurs à la voix entreprise locale](enable-the-users-for-enterprise-voice-on-premises.md) (exécutée lorsque les utilisateurs sont hébergés sur site). 
  
Tous les utilisateurs doivent être créés dans Active Directory en local et synchronisés avec Office 365 à l’aide de la version prise en charge d’Azure AD Connector. Vous ne pouvez pas activer les utilisateurs pour le système téléphonique dans Office 365 qui ont été créés directement dans Azure AD. Si vous voulez activer le système téléphonique dans Office 365 avec la connectivité PSTN locale pour un utilisateur qui a été créé dans Azure AD, vous devez créer un nouveau compte pour cet utilisateur dans votre annonce locale, configurer le compte en local, puis synchroniser le compte à l’aide de une version prise en charge de l’outil Azure AD Connector. 
  
L’activation d’un utilisateur pour système téléphonique dans Office 365 avec une connectivité PSTN locale, puis la transition vers Skype entreprise Online nécessite les étapes suivantes :
  
- [Autorisez les utilisateurs à utiliser les fonctionnalités vocales d’entreprise](enable-the-users-for-enterprise-voice-on-premises.md) (effectuées lorsque les utilisateurs sont hébergés sur site).
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (lorsque les utilisateurs sont hébergés en local).
    
- [Synchroniser les utilisateurs avec le Cloud et affecter des licences](synchronize-users-to-the-cloud-and-assign-licenses.md) (exécutées à l’aide d’Office 365).
    
- [Déplacez les utilisateurs locaux vers Skype entreprise Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (exécuté à l’aide de Windows PowerShell local, mais à l’aide de vos informations d’identification d’administrateur 365 Office).
    
- [Activez les utilisateurs d’Enterprise Voice Online et du système téléphonique dans Office 365 boîte vocale](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (exécuté à l’aide de Remote PowerShell.
    

