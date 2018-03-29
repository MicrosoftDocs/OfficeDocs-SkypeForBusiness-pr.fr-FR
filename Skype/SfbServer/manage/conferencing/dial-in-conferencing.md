---
title: Gestion des conférences rendez-vous dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Résumé : Apprenez à gérer dans l’accès à la conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: 44427a9109fd061233d1c8676166788e162c7e08
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server-2015"></a>Gestion des conférences rendez-vous dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à gérer dans l’accès à la conférence dans Skype pour Business Server 2015.
  
Cette rubrique décrit comment gérer la conférence rendez-vous. Pour plus d’informations sur la façon de planifier et de configurer les conférences de connexion au moment du déploiement, consultez le [Plan pour les conférences à distance dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/dial-in-conferencing.md) et [configurer à distance conférence dans Skype pour Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Vous pouvez effectuer les tâches suivantes pour gérer les conférences à distance : activer ou désactiver dans l’accès à la conférence, gérer des numéros d’accès, gérer les stratégies de code PIN pour les appels en conférence, gérer la jointure de la conférence et laissez les annonces, modifier les mappages de clés de DTMF commandes et les utilisateurs bienvenues aux conférences en accès à distance. 
  
Pour plus d’informations sur la gestion des plans de numérotation, consultez [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Pour plus d’informations sur l’utilisation des TLS, consultez [configurer les stratégies de voix, les enregistrements d’utilisation de TLS et les itinéraires de voix dans Skype pour entreprise 2015](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Gérer des conférences à distance à l’aide de Skype pour le panneau de configuration de Business Server

Pour gérer les informations d’une conférence rendez-vous :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférences**.
    
Pour gérer les informations sur les plans de numérotation et l’utilisation RTC :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Gérer des conférences à distance à l’aide de Skype pour Business Server Management Shell

Pour gérer des conférences à distance à l’aide de Skype pour Business Server Management Shell, utilisez les applets de commande suivantes :
  
**Paramètres de configuration à distance**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Renvoie des informations sur les annuaires de conférences configurés pour être utilisés dans votre organisation. Les annuaires des conférences permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Récupère les informations sur la façon dont Skype pour Business Server répond lorsque les utilisateurs rejoindre ou quittent une conférence à distance.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retourne des informations sur tous les numéros d’accès de conférence rendez-vous configurés en vue d’une utilisation dans votre organisation.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Renvoie les paramètres de signalisation DTMF (Dual-Tone Multifrequency ou numérotation en fréquences vocales) utilisés pour la conférence rendez-vous. Le système DTMF permet aux utilisateurs qui rejoignent une conférence d’en contrôler les paramètres (comme la capacité de mettre en sourdine, de verrouiller ou de déverrouiller la conférence) à l’aide du clavier du téléphone.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Retourne une liste de langages, y compris les langues régionales/minoritaires, pris en charge pour une utilisation avec Skype pour Business Server à distance des participants. Ces langues sont utilisées pour relayer les messages audio et les instructions aux utilisateurs participant à la conférence grâce à un numéro de téléphone.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retourne des informations sur les plans de numérotation utilisés au sein de votre organisation.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Affecte un plan de numérotation à un ou plusieurs utilisateurs ou groupes.  <br/> |
|[Importation-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importe les répertoires de conférence à partir de Microsoft Office Communications Server 2007 R2 à Skype pour Business Server. Cela permet d’assurer l’interopérabilité entre Skype pour Business Server et Office Communications Server 2007 R2.  <br/> |
|[Déplacement-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Déplace un annuaire des conférences existant d’un pool vers un autre.  <br/> |
|[Nouvelle-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crée un annuaire de conférence en vue de l’utiliser dans votre organisation.  <br/> |
|[Nouvelle-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crée un nouveau numéro d’accès à la conférence rendez-vous.  <br/> |
|[Nouvelle-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration pour la conférence rendez-vous. Ces paramètres déterminent comment Skype pour Business Server répond lorsque les utilisateurs rejoindre ou quittent une conférence à distance. Sont renvoyées en particulier des informations qui indiquent si les participants sont tenus ou non d’enregistrer leur nom en rejoignant la conférence et comment (ou si) le système doit annoncer qu’une personne a rejoint la conférence ou l’a quittée.  <br/> |
|[Nouvelle-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Crée une collection de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences rendez-vous.  <br/> |
|[Nouvelle-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crée un nouveau plan de numérotation.  <br/> |
|[Supprimer-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Supprime un annuaire des conférences existant.  <br/> |
|[Supprimer-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Supprime un numéro d’accès à une conférence rendez-vous existant.  <br/> |
|[Supprimer-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Supprime une ou plusieurs collections de paramètres de configuration de conférence rendez-vous. Ces paramètres déterminent comment Skype pour Business Server répond lorsque les utilisateurs rejoindre ou quittent une conférence à distance.  <br/> |
|[Supprimer-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Supprime une collection de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences rendez-vous.  <br/> |
|[Ensemble-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifie les valeurs de propriétés d’un numéro d’accès de conférence rendez-vous existant.  <br/> |
|[Ensemble-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifie les paramètres qui déterminent comment Skype pour Business Server répond lorsque les utilisateurs rejoindre ou quittent une conférence à distance.  <br/> |
|[Ensemble-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifie les paramètres de signalisation DTMF (Dual Tone Multi-Frequency) de la conférence rendez-vous.  <br/> |
|[Ensemble-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifie un plan de numérotation existant.  <br/> |
   
**Paramètres de stratégie de code PIN**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Renvoie des informations sur les stratégies d’authentification par code confidentiel des clients configurées pour être utilisées dans votre organisation. SON authentification permet aux utilisateurs d’accéder à Skype pour serveur d’entreprise en fournissant un code PIN au lieu d’un nom d’utilisateur et le mot de passe.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Affecte une stratégie cliente de code confidentiel à un utilisateur ou un groupe d’utilisateurs.  <br/> |
|[Nouvelle-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crée une stratégie d’authentification par code confidentiel pour les clients.  <br/> |
|[Supprimer-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Supprime la stratégie de code confidentiel.  <br/> |
|[Ensemble-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifie une ou plusieurs stratégies d’authentification par code confidentiel existantes pour les clients.  <br/> |
   

