---
title: Gérer les conférences téléphoniques dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Résumé : Découvrez comment gérer les conférences téléphoniques dans Skype Entreprise Server.'
ms.openlocfilehash: 3c6f72d3e2c5e19ef970e7d8e5410dcc9cad2d14
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772060"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Gérer les conférences téléphoniques dans Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer les conférences téléphoniques dans Skype Entreprise Server.
  
Cette rubrique décrit comment gérer les conférences téléphoniques. Pour plus d’informations sur la façon de planifier et de configurer la conférence rendez-vous lors du déploiement, voir [Plan for dial-in conferencing in Skype Entreprise Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) and [Configure dial-in conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Vous pouvez effectuer les tâches suivantes pour gérer les conférences dial-in : activer ou désactiver la conférence d’accès, gérer les numéros d’accès, gérer les stratégies de code confidentiel pour les conférences téléphoniques, gérer les annonces de connexion et de départ de conférence, modifier les mappages de touches pour les commandes DTMF et accueillir les utilisateurs à la conférence téléphonique. 
  
Pour plus d’informations sur la gestion des plans de numérotation, voir Créer ou modifier un plan de numérotation [dans Skype Entreprise Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Pour plus d’informations sur l’utilisation PSTN, voir [Configure voice policies, PSTN usage records, and voice routes in Skype Entreprise](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Gérer les conférences téléphoniques à l’aide du Skype Entreprise Server de contrôle

Pour gérer les informations sur les conférences téléphoniques :
  
1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**.
    
Pour gérer les informations sur les plans de numérotation et l’utilisation PSTN :
  
1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez **sur Routage des voix.**
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Gérer les conférences téléphoniques à l’aide de Skype Entreprise Server Management Shell

Pour gérer les conférences téléphoniques à l’aide Skype Entreprise Server Management Shell, utilisez les cmdlets suivantes :
  
**Paramètres de configuration de la connexion**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Retourne des informations sur les annuaires de conférences configurés pour être utilisés dans votre organisation. Les annuaires des conférences permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Récupère des informations sur la façon dont Skype Entreprise Server répond lorsque des utilisateurs rejoignent ou quittent une conférence téléphonique.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retourne des informations sur tous les numéros d’accès aux conférences téléphoniques configurés pour être utilisés dans votre organisation.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Renvoie les paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences téléphoniques. DTMF permet aux utilisateurs qui prennent part à une conférence de contrôler les paramètres de conférence (tels que l’activation et la désactivation de leur microphone ou le verrouillage et le déverrouillage de la conférence) à l’aide du clavier de leur téléphone.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Renvoie une liste de langues, y compris les langues régionales/étrangères, pris en charge pour une Skype Entreprise Server conférences téléphoniques. Ces langues sont utilisées pour relayer les messages audio et les instructions aux utilisateurs participant à la conférence grâce à un numéro de téléphone.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retourne des informations sur les plans de numérotation utilisés au sein de votre organisation.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Affecte un plan de numérotation à un ou plusieurs utilisateurs ou groupes.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importe les annuaires des conférences Microsoft Office Communications Server 2007 R2 vers Skype Entreprise Server. Cela permet d’assurer l’interopérabilité entre Skype Entreprise Server et Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Déplace un annuaire de conférence existant d’un pool vers un autre.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crée un annuaire de conférence en vue de l’utiliser dans votre organisation.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crée un nouveau numéro d’accès à la conférence rendez-vous.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration pour la conférence rendez-vous. Ces paramètres déterminent le Skype Entreprise Server réponse des utilisateurs qui rejoignent ou quittent une conférence téléphonique. Sont retournées en particulier les informations qui indiquent si les participants sont tenus ou non d’enregistrer leur nom en rejoignant la conférence et comment (ou si) le système doit annoncer qu’une personne a rejoint la conférence ou l’a quittée.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Crée une collection de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences téléphoniques.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crée un nouveau plan de numérotation.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Supprime un annuaire de conférence existant.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Supprime un numéro d’accès à une conférence rendez-vous existant.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Supprime une ou plusieurs collections de paramètres de configuration de conférence rendez-vous. Ces paramètres déterminent le Skype Entreprise Server réponse des utilisateurs qui rejoignent ou quittent une conférence téléphonique.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Supprime une collection existante de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences rendez-vous.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifie les valeurs de propriétés d’un numéro d’accès de conférence rendez-vous existant.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifie les paramètres qui déterminent le Skype Entreprise Server lorsque les utilisateurs rejoignent ou quittent une conférence téléphonique.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifie les paramètres de signalisation DTMF (Dual Tone Multi-Frequency) de la conférence rendez-vous.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifie un plan de numérotation existant.  <br/> |
   
**Paramètres de stratégie de code confidentiel**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Retourne des informations sur les stratégies d’authentification par code confidentiel des clients configurées pour être utilisées dans votre organisation. L’authentification par code confidentiel permet aux utilisateurs d’accéder Skype Entreprise Server en fournissant un code confidentiel au lieu d’un nom d’utilisateur et d’un mot de passe.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Affecte une stratégie cliente de code confidentiel à un utilisateur ou un groupe d’utilisateurs.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crée une stratégie d’authentification par code confidentiel pour les clients.  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Supprime la stratégie de code confidentiel.  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifie une ou plusieurs stratégies de code confidentiel (PIN) client existantes.  <br/> |
