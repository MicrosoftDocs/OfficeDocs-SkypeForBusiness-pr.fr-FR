---
title: Permettre aux utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN local dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Cette rubrique décrit comment permettre aux utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN sur site. Avant de suivre les étapes décrites dans cette rubrique, vous devez voir les articles suivants :.
ms.openlocfilehash: 7427bf33c275d55b99c240aaf192d180c2d63945
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2019
ms.locfileid: "30642204"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Permettre aux utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN local dans Skype pour Business Server
 
Cette rubrique décrit comment permettre aux utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN sur site. Avant de suivre les étapes décrites dans cette rubrique, vous devez voir les articles suivants :.
  
- Pour savoir comment configurer la connectivité hybride, consultez [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et [déployer la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Pour plus d’informations sur la planification de votre déploiement, voir [Planifier le système téléphonique dans Office 365 avec une connectivité PSTN dans Skype pour Business Server local](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Pour en savoir plus sur le système téléphonique dans Office 365, notamment la gestion des licences et plans, voir [appel PSTN de plans de Skype pour les entreprises](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Déplacement d’utilisateurs au système téléphonique dans Office 365 avec une connectivité PSTN sur site

Avant de déplacer vos utilisateurs à Skype pour Business Online, il est recommandé que vous activez vos utilisateurs sur site dans Skype pour Business Server ou Microsoft Lync Server 2013 et les déplacez en ligne. Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business en ligne](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et à la section Considérations spéciales [d’Activer les utilisateurs pour Enterprise Voice sur site](enable-the-users-for-enterprise-voice-on-premises.md). 
  
Tous les utilisateurs doivent être créés dans Active Directory sur site et synchronisés avec Office 365 à l’aide de la version prise en charge d’Azure AD connecteur. Vous ne pouvez pas activer les utilisateurs pour système téléphonique dans Office 365 qui ont été créées directement dans Azure AD. Si vous souhaitez activer le système téléphonique dans Office 365 avec une connectivité PSTN pour un utilisateur qui a été créé dans Azure AD sur site, vous devez créer un nouveau compte de cet utilisateur dans votre environnement local AD, configurer le compte local, puis synchroniser le compte à l’aide une version prise en charge de l’outil Azure AD connecteur. 
  
Permettre à un utilisateur pour le système téléphonique dans Office 365 avec une connectivité PSTN sur site et les déplacer vers Skype pour Business Online nécessitent les étapes suivantes :
  
- [Activez les utilisateurs pour Enterprise Voice sur site](enable-the-users-for-enterprise-voice-on-premises.md) (opération réalisée alors que les utilisateurs sont hébergés sur un système local).
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (lorsque les utilisateurs sont hébergés en local).
    
- [Synchroniser les utilisateurs pour les nuage et attribuer des licences](synchronize-users-to-the-cloud-and-assign-licenses.md) (opération réalisée à l’aide d’Office 365).
    
- [Déplacer des utilisateurs sur site à Skype pour Business Online](move-on-premises-users-to-skype-for-business-online.md) (opération réalisée à l’aide de Windows PowerShell local, mais à l’aide de vos informations d’identification d’administrateur Office 365).
    
- [Activer les utilisateurs pour Enterprise Voice en ligne et le système téléphonique dans la messagerie Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (opération réalisée à l’aide de PowerShell à distance).
    

