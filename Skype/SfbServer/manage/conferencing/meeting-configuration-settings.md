---
title: Gestion des paramètres de configuration de réunion dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Résumé : Apprenez à gérer les paramètres de configuration dans Skype pour Business Server 2015 de réunion.'
ms.openlocfilehash: 30b19eee5e298bfaa5eefe1eee50c9ea615b5682
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Gestion des paramètres de configuration de réunion dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à gérer les paramètres de configuration dans Skype pour Business Server 2015 de réunion.
  
Cette rubrique décrit comment gérer les paramètres de configuration de réunion. Pour plus d’informations sur la façon de planifier et de déployer des conférences, voir [conférences de déployer dans Skype pour Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md)et de [Plan pour les conférences dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) .
  
Les paramètres de configuration de réunion dictent le type de réunions que les utilisateurs peuvent créer, contrôler comment (ou même si) les utilisateurs anonymes et les utilisateurs d’accès à la conférence peuvent joindre à ces réunions. Notez que ces paramètres n’affectent que les réunions planifiées ; elles n’affectent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans Skype pour les entreprises.
  
Les paramètres de configuration de réunion définissent ce qui suit :
  
- si les appels émis à partir d’un du réseau téléphonique commuté (PSTN) sont transférés vers la salle d’attente ;
    
- qui peut être présentateur ;
    
- si le type de conférence est affecté par défaut ;
    
- si les utilisateurs anonymes (non authentifiés) sont admis par défaut.
    
Vous pouvez définir les caractéristiques des réunions à l’aide de Skype pour le panneau de configuration de Business Server ou à l’aide de Skype pour Business Server Management Shell. 
  
Vous pouvez spécifier des paramètres au niveau global (créé par défaut) de la réunion, au niveau du site ou au niveau du pool. Par défaut, les paramètres globaux définissent l’expérience de réunion. Si vous créez des paramètres au niveau du pool, ceux-ci s’appliquent à toutes les réunions hébergées par ce pool. Si vous ne créez pas de paramètres au niveau du pool, les paramètres définis au niveau du site s’appliquent, s’ils existent. Si aucun paramètre n’a été défini au niveau du site, les paramètres globaux s’appliquent à l’ensemble des réunions.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Gérer les paramètres de réunion pour le panneau de configuration de Business Server à l’aide de Skype

Pour gérer les paramètres de la réunion pour le panneau de configuration de Business Server à l’aide de Skype :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Gérer les paramètres de réunion pour Business Server Management Shell à l’aide de Skype

Pour gérer des réunions à l’aide de Skype pour Business Server Management Shell, utilisez les applets de commande suivantes :
  
**Paramètres de configuration de réunion**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Renvoie des informations sur les paramètres de configuration de réunion actuellement utilisés dans votre organisation.  <br/> |
|[Nouvelle-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de réunion au niveau de l’étendue du site ou du service.  <br/> |
|[Supprimer-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Supprime une collection existante de paramètres de configuration de réunion.  <br/> |
|[Ensemble-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifie les paramètres de configuration de réunion actuellement utilisés dans votre organisation.  <br/> |
   

