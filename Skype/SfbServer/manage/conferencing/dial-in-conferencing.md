---
title: Gérer les conférences rendez-vous dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Résumé : Découvrez comment gérer les conférences rendez-vous dans Skype pour Business Server.'
ms.openlocfilehash: dac805421539116f89e007c68689ffd89400d059
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969637"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Gérer les conférences rendez-vous dans Skype pour Business Server
 
**Résumé :** Découvrez comment gérer les conférences rendez-vous dans Skype pour Business Server.
  
Cette rubrique décrit comment gérer la conférence rendez-vous. Pour plus d’informations sur la façon de planifier et configurer la conférence rendez-vous au moment du déploiement, voir [planifier des conférences rendez-vous dans Skype pour Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) et les [configurer dans les conférences rendez-vous dans Skype pour Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Vous pouvez effectuer les tâches suivantes pour gérer les conférences rendez-vous : activer ou désactiver la conférence rendez-vous, gérer les numéros d’accès, gérer les stratégies de code confidentiel pour les conférences rendez-vous, gérer la participation à une conférence et laissez des annonces, modifier les mappages de touches pour DTMF commandes et Bienvenue aux utilisateurs de conférence rendez-vous. 
  
Pour plus d’informations sur la gestion des plans de numérotation, voir [créer ou modifier un plan de numérotation dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Pour plus d’informations sur l’utilisation PSTN, voir [configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour les entreprises](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Gérer les conférences rendez-vous à l’aide de Skype pour Business Server Control Panel

Pour gérer les informations d’une conférence rendez-vous :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférences**.
    
Pour gérer les informations sur les plans de numérotation et l’utilisation RTC :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Gérer les conférences rendez-vous à l’aide de Skype pour Business Server Management Shell

Pour gérer les conférences rendez-vous à l’aide de Skype pour Business Server Management Shell, utilisez les applets de commande suivantes :
  
**Paramètres de configuration des conférences rendez-vous**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Renvoie des informations sur les annuaires de conférences configurés pour être utilisés dans votre organisation. Les annuaires des conférences permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Récupère des informations sur comment Skype pour Business Server répond lorsque les utilisateurs rejoignent ou quittent une conférence rendez-vous.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retourne des informations sur tous les numéros d’accès de conférence rendez-vous configurés en vue d’une utilisation dans votre organisation.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Renvoie les paramètres de signalisation DTMF (Dual-Tone Multifrequency ou numérotation en fréquences vocales) utilisés pour la conférence rendez-vous. Le système DTMF permet aux utilisateurs qui rejoignent une conférence d’en contrôler les paramètres (comme la capacité de mettre en sourdine, de verrouiller ou de déverrouiller la conférence) à l’aide du clavier du téléphone.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Renvoie une liste des langues, notamment les langues régionales/minoritaires, pris en charge pour une utilisation avec Skype pour les conférences rendez-vous Business Server. Ces langues sont utilisées pour relayer les messages audio et les instructions aux utilisateurs participant à la conférence grâce à un numéro de téléphone.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retourne des informations sur les plans de numérotation utilisés au sein de votre organisation.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Affecte un plan de numérotation à un ou plusieurs utilisateurs ou groupes.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importe les annuaires des conférences à partir de Microsoft Office Communications Server 2007 R2 vers Skype pour Business Server. Cela permet d’assurer l’interopérabilité entre Skype pour Business Server et Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Déplace un annuaire des conférences existant d’un pool vers un autre.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crée un annuaire de conférence en vue de l’utiliser dans votre organisation.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crée un nouveau numéro d’accès à la conférence rendez-vous.  <br/> |
|[Nouvelle-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration pour la conférence rendez-vous. Ces paramètres déterminent comment Skype pour Business Server répond lorsque les utilisateurs rejoignent ou quittent une conférence rendez-vous. Sont renvoyées en particulier des informations qui indiquent si les participants sont tenus ou non d’enregistrer leur nom en rejoignant la conférence et comment (ou si) le système doit annoncer qu’une personne a rejoint la conférence ou l’a quittée.  <br/> |
|[Nouvelle-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Crée une collection de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences rendez-vous.  <br/> |
|[Nouvelle-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crée un nouveau plan de numérotation.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Supprime un annuaire des conférences existant.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Supprime un numéro d’accès à une conférence rendez-vous existant.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Supprime une ou plusieurs collections de paramètres de configuration de conférence rendez-vous. Ces paramètres déterminent comment Skype pour Business Server répond lorsque les utilisateurs rejoignent ou quittent une conférence rendez-vous.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Supprime une collection de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences rendez-vous.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifie les valeurs de propriétés d’un numéro d’accès de conférence rendez-vous existant.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifie les paramètres qui déterminent comment Skype pour Business Server répond lorsque les utilisateurs rejoignent ou quittent une conférence rendez-vous.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifie les paramètres de signalisation DTMF (Dual Tone Multi-Frequency) de la conférence rendez-vous.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifie un plan de numérotation existant.  <br/> |
   
**Paramètres de stratégie de code confidentiel**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Renvoie des informations sur les stratégies d’authentification par code confidentiel des clients configurées pour être utilisées dans votre organisation. Authentification par code confidentiel permet aux utilisateurs d’accéder à Skype pour Business Server en fournissant un code confidentiel au lieu d’un nom d’utilisateur et le mot de passe.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Affecte une stratégie cliente de code confidentiel à un utilisateur ou un groupe d’utilisateurs.  <br/> |
|[Nouvelle-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crée une stratégie d’authentification par code confidentiel pour les clients.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Supprime la stratégie de code confidentiel.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifie une ou plusieurs stratégies d’authentification par code confidentiel existantes pour les clients.  <br/> |
   

