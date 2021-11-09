---
title: Gérer les paramètres de configuration de réunion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Résumé : Découvrez comment gérer les paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: ccbb1a43364ddd5507fb01c59000397130a9c22e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832098"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Gérer les paramètres de configuration de réunion dans Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer les paramètres de configuration de réunion dans Skype Entreprise Server.
  
Cette rubrique décrit comment gérer les paramètres de configuration de réunion. Pour plus d’informations sur la façon de planifier et de déployer des conférences, voir [Plan for conferencing in Skype Entreprise Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Les paramètres de configuration de réunion déterminent le type de réunion que les utilisateurs peuvent créer, en plus de contrôler comment (ou même si) les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent participer à ces réunions. Notez que ces paramètres affectent uniquement les réunions prévues ; elles n’affectent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans Skype Entreprise.
  
Les paramètres de configuration de réunion définissent les paramètres suivants :
  
- si les appels émis à partir d’un du réseau téléphonique commuté (PSTN) sont transférés vers la salle d’attente ;
    
- qui peut être présentateur ;
    
- si le type de conférence est affecté par défaut ;
    
- si les utilisateurs anonymes (non authentifiés) sont admis par défaut.
    
Vous pouvez définir les caractéristiques des réunions à l’Skype Entreprise Server du Panneau de Skype Entreprise Server ou à l’aide Skype Entreprise Server Management Shell. 
  
Vous pouvez spécifier les paramètres de réunion au niveau global (créé par défaut), au niveau du site ou au niveau du pool. Par défaut, les paramètres globaux définissent l’expérience de réunion. Si vous créez des paramètres au niveau du pool, ceux-ci s’appliquent à toutes les réunions hébergées par ce pool. Si vous ne créez pas de paramètres au niveau du pool, les paramètres au niveau du site s’appliquent s’ils existent. Si vous ne définissez pas de paramètres au niveau du site, les paramètres globaux s’appliquent à toutes les réunions.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Gérer les paramètres de réunion à l’aide Skype Entreprise Server panneau de configuration

Pour gérer les paramètres de réunion à l’aide Skype Entreprise Server panneau de configuration :
  
1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Configuration de **la réunion.**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Gérer les paramètres de réunion à l’aide Skype Entreprise Server Management Shell

Pour gérer les réunions à l’aide Skype Entreprise Server Management Shell, utilisez les cmdlets suivantes :
  
**Paramètres de configuration des réunions**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Retourne des informations sur les paramètres de configuration de réunion actuellement utilisés dans votre organisation.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de réunion au niveau de l’étendue Site ou Service.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Supprime une collection existante de paramètres de configuration de réunion.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifie les paramètres de configuration de réunion actuellement utilisés dans votre organisation.  <br/> |
