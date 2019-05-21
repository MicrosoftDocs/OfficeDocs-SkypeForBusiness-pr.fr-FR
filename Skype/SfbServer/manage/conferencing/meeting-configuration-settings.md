---
title: Gérer les paramètres de configuration de la réunion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Résumé: Découvrez comment gérer les paramètres de configuration de la réunion dans Skype entreprise Server.'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283738"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Gérer les paramètres de configuration de la réunion dans Skype entreprise Server
 
**Résumé:** Découvrez comment gérer les paramètres de configuration de la réunion dans Skype entreprise Server.
  
Cette rubrique décrit comment gérer les paramètres de configuration de réunion. Pour plus d’informations sur la planification et le déploiement de conférences, voir [planifier les conférences dans Skype entreprise Server](../../plan-your-deployment/conferencing/conferencing.md) et [déployer des conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Les paramètres de configuration de réunion déterminent le type de réunion que les utilisateurs peuvent créer, en plus de contrôler la façon dont les utilisateurs anonymes et les conférences rendez-vous peuvent participer à ces réunions. Notez que ces paramètres affectent uniquement les réunions planifiées; Il n’y a pas d’incidence sur les réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans Skype entreprise.
  
Les paramètres de configuration de réunion définissent ce qui suit :
  
- si les appels émis à partir d’un du réseau téléphonique commuté (PSTN) sont transférés vers la salle d’attente ;
    
- qui peut être présentateur ;
    
- si le type de conférence est affecté par défaut ;
    
- si les utilisateurs anonymes (non authentifiés) sont admis par défaut.
    
Vous pouvez définir les caractéristiques des réunions à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell. 
  
Vous pouvez spécifier les paramètres de la réunion au niveau global (créé par défaut), au niveau du site ou au niveau du pool. Par défaut, les paramètres globaux définissent l’expérience de réunion. Si vous créez des paramètres au niveau du pool, ceux-ci s’appliquent à toutes les réunions hébergées par ce pool. Si vous ne créez pas de paramètres au niveau du pool, les paramètres définis au niveau du site s’appliquent, s’ils existent. Si aucun paramètre n’a été défini au niveau du site, les paramètres globaux s’appliquent à l’ensemble des réunions.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Gérer les paramètres de la réunion à l’aide du panneau de configuration Skype entreprise Server

Pour gérer les paramètres de la réunion à l’aide du panneau de configuration Skype entreprise Server, procédez comme suit:
  
1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Gérer les paramètres de la réunion à l’aide de Skype entreprise Server Management Shell

Pour gérer les réunions à l’aide de Skype entreprise Server Management Shell, utilisez les applets de commande suivantes:
  
**Paramètres de configuration des réunions**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Renvoie des informations sur les paramètres de configuration de réunion actuellement utilisés dans votre organisation.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de réunion au niveau de l’étendue du site ou du service.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Supprime une collection existante de paramètres de configuration de réunion.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifie les paramètres de configuration de réunion actuellement utilisés dans votre organisation.  <br/> |
   

