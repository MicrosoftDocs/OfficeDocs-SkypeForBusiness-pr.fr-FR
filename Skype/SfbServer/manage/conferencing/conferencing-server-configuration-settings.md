---
title: Gestion des paramètres de configuration du serveur de conférence dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Résumé : Apprenez à gérer les paramètres de configuration serveur conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: 88c127acdd569945eddb41e997034e5ea23ea2a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server-2015"></a>Gestion des paramètres de configuration du serveur de conférence dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à gérer les paramètres de configuration serveur conférence dans Skype pour Business Server 2015.
  
Cette rubrique décrit comment gérer paramètres de configuration de conférence. Pour plus d’informations sur la façon de planifier et de déployer des conférences, voir [conférences de déployer dans Skype pour Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md)et de [Plan pour les conférences dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) .
  
Les paramètres de configuration de Conferencing déterminent des éléments tels que la taille maximale autorisée pour le contenu de la réunion et des documents ; quantité maximale de bande passante pour le service de conférence de partage d’Application ; limites de stockage et les périodes d’expiration ; les URL d’interne et externe des téléchargements du client pris en charge ; pointeurs vers les URL internes et externes, où les utilisateurs peuvent obtenir aide de conférence et de ressources ; et les ports utilisés pour le partage d’application, client audio, transferts de fichiers et le trafic multimédia. Ces paramètres vous permettent de gérer les serveurs eux-mêmes. Ces paramètres peuvent être définis à l’aide de Skype pour Business Server Management Shell.
  
Lorsque vous installez Skype pour Business Server, le système vous propose une collection unique de la conférence des paramètres de configuration (la collection globale). Si vous avez besoin créer des paramètres personnalisés pour un site ou un service, vous pouvez le faire à l’aide de l’applet de commande **New-CsConferencingConfiguration** . Notez que les nouveaux paramètres peuvent être appliquées uniquement à la portée de site ou un service ; Vous ne pouvez pas créer une nouvelle collection globale de la conférence des paramètres de configuration, mais vous pouvez modifier la collection globale à l’aide de l’applet de commande **Set-CsConferencingConfiguration** . En outre, aucun site ou un service ne peut héberger des plus d’une collection de paramètres. Si vous essayez de créer de nouveaux paramètres pour le Redmond site et le Redmond site héberge déjà un ensemble de paramètres de configuration de conférence, puis votre commande ne pourra pas.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gérer les paramètres de configuration de conférence pour Business Server Management Shell à l’aide de Skype

Pour gérer les paramètres de configuration de conférence à l’aide de Skype pour Business Server Management Shell, utilisez les applets de commande suivantes :
  
**Paramètres de configuration de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Renvoie des informations sur les paramètres de configuration de conférence de votre organisation.  <br/> |
|[Nouvelle-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de conférence.  <br/> |
|[Supprimer-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Supprime la collection spécifiée des paramètres de configuration de conférence.  <br/> |
|[Ensemble-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifie une collection existante de paramètres de configuration de conférence.  <br/> |
   
La commande ci-dessous crée une collection de paramètres de configuration de conférence pour le site Redmond (site:Redmond). Dans cet exemple, un paramètre supplémentaire a été inclus (Organization). Celui-ci définit la valeur de la propriété Organization sur Litwareinc : 
  
```
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc

```

Notez que vous êtes limité à une seule collection par site, si bien que cette commande échoue si le site Redmond comporte déjà une collection de paramètres de configuration de conférence. 
  
L’exemple ci-dessous définit une nouvelle collection de paramètres de configuration de conférence, qui sont initialement stockés en mémoire, puis ultérieurement appliqués au site de Redmond. 
  
La première commande utilise l’applet de commande **New-CsConferencingConfiguration** pour créer une collection de paramètres en mémoire stockée dans la variable $x. Le paramètre InMemory spécifie que la collection doit être créée en mémoire au lieu d’être immédiatement appliquée au site Redmond.
  
Une fois la collection créée, la deuxième commande définit la valeur de la propriété Organization sur Litwareinc. 
  
Enfin, la troisième commande utilise l’applet de commande **Set-CsConferencingConfiguration** pour appliquer les nouveaux paramètres au site Redmond :
  
```
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x

```

Si vous n’appelez pas l’applet de commande **Set-CsConferencingConfiguration**, les nouveaux paramètres ne s’appliquent pas. Ils disparaissent dès que vous mettez fin à votre session nm-winshell-2nd ou supprimez la variable $x.
  

