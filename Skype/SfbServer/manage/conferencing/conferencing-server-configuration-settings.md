---
title: Gérer les paramètres de configuration serveur conférence dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Résumé : Découvrez comment gérer les paramètres de configuration serveur conférence dans Skype pour Business Server.'
ms.openlocfilehash: a12226f9f7d56f9f8a61b6f820a2c0f9744121fc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222841"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Gérer les paramètres de configuration serveur conférence dans Skype pour Business Server
 
**Résumé :** Découvrez comment gérer les paramètres de configuration serveur conférence dans Skype pour Business Server.
  
Cette rubrique décrit comment gérer paramètres de configuration de conférence. Pour plus d’informations sur la façon de planifier et déployer la conférence, voir [Plan pour la conférence dans Skype pour Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conférence dans Skype pour Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Déterminent les paramètres de configuration de conférence des éléments tels que la taille maximale autorisée pour le contenu des réunions et des documents ; quantité maximale de bande passante pour le service de conférence de partage d’Application ; limites de stockage et les périodes d’expiration ; les URL internes et externes pour les téléchargements du client prises en charge ; pointeurs vers des URL internes et externes, où les utilisateurs peuvent obtenir aide de conférence et des ressources ; et les ports utilisés pour le partage d’application, audio client, transferts de fichiers et le trafic multimédia. Ces paramètres vous permettent de gérer les serveurs eux-mêmes. Ces paramètres peuvent être définis à l’aide de Skype pour Business Server Management Shell.
  
Lorsque vous installez Skype pour Business Server, le système vous fournit une collection unique de la conférence (la collection globale) les paramètres de configuration. Si vous avez besoin créer des paramètres personnalisés pour un site ou service, vous pouvez le faire à l’aide de l’applet de commande **New-CsConferencingConfiguration** . Notez que les nouveaux paramètres peuvent être appliqués uniquement au niveau du site ou service ; Vous ne pouvez pas créer une nouvelle collection globale de conférence des paramètres de configuration, mais vous pouvez modifier la collection globale à l’aide de l’applet de commande **Set-CsConferencingConfiguration** . En outre, aucun site ou service ne peut héberger plusieurs collections de paramètres. Si vous essayez de pour créer des paramètres pour le Redmond site et le Redmond site héberge déjà une collection de paramètres de configuration de conférence, puis votre commande échouera.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gérer les paramètres de configuration de conférence à l’aide de Skype pour Business Server Management Shell

Pour gérer les paramètres de configuration de conférence à l’aide de Skype pour Business Server Management Shell, utilisez les applets de commande suivantes :
  
**Paramètres de configuration de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Renvoie des informations sur les paramètres de configuration de conférence de votre organisation.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de conférence.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Supprime la collection spécifiée des paramètres de configuration de conférence.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifie une collection existante de paramètres de configuration de conférence.  <br/> |
   
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
  

