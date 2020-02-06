---
title: Gérer les paramètres de configuration du serveur de conférence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Résumé : Découvrez comment gérer les paramètres de configuration de serveur de conférence dans Skype entreprise Server.'
ms.openlocfilehash: c43734a2d79bf07023486eb163fff7bbef56e73f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818635"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Gérer les paramètres de configuration du serveur de conférence dans Skype entreprise Server
 
**Résumé :** Découvrez comment gérer les paramètres de configuration de serveur de conférence dans Skype entreprise Server.
  
Cette rubrique décrit comment gérer paramètres de configuration de conférence. Pour plus d’informations sur la planification et le déploiement de conférences, voir [planifier les conférences dans Skype entreprise Server](../../plan-your-deployment/conferencing/conferencing.md) et [déployer des conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Les paramètres de configuration de conférences déterminent des éléments tels que la taille maximale autorisée pour le contenu et les documents de la réunion. quantité maximale de bande passante pour le service de conférence de partage d’application ; limites de stockage et périodes d’expiration ; URL des téléchargements internes et externes du client pris en charge ; pointe vers des URL internes et externes où les utilisateurs peuvent obtenir de l’aide et des ressources de conférence ; les ports utilisés pour le partage d’application, le son du client, le transfert de fichiers et le trafic multimédia. Ces paramètres vous permettent de gérer les serveurs eux-mêmes. Ces paramètres peuvent être définis à l’aide de Skype entreprise Server Management Shell.
  
Lorsque vous installez Skype entreprise Server, le système vous propose une collection unique de paramètres de configuration de conférence (collection globale). Si vous devez créer des paramètres personnalisés pour un site ou un service, vous pouvez le faire à l’aide de l’applet **de nouvelle cmdlet New-CsConferencingConfiguration** . Notez que les nouveaux paramètres peuvent être appliqués uniquement à l’étendue du site ou du service ; vous ne pouvez pas créer de nouvelle collection globale de paramètres de configuration de conférence, mais vous pouvez modifier la collection globale à l’aide de l’applet de passe **Set-CsConferencingConfiguration** . De plus, le service ou le site ne peut pas héberger plus d’une collection de paramètres. Si vous tentez de créer de nouveaux paramètres pour le site de Redmond et que le site de Redmond héberge déjà une collection de paramètres de configuration des conférences, votre commande échoue.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gestion des paramètres de configuration des conférences à l’aide de Skype entreprise Server Management Shell

Pour gérer les paramètres de configuration des conférences à l’aide de Skype entreprise Server Management Shell, utilisez les applets de commande suivantes :
  
**Paramètres de configuration de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Renvoie des informations sur les paramètres de configuration de conférence de votre organisation.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de conférence.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Supprime la collection spécifiée des paramètres de configuration de conférence.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifie une collection existante de paramètres de configuration de conférence.  <br/> |
   
La commande ci-dessous crée une collection de paramètres de configuration de conférence pour le site Redmond (site:Redmond). Dans cet exemple, un paramètre supplémentaire a été inclus (Organization). Celui-ci définit la valeur de la propriété Organization sur Litwareinc : 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Notez que vous êtes limité à une seule collection par site, si bien que cette commande échoue si le site Redmond comporte déjà une collection de paramètres de configuration de conférence. 
  
L’exemple ci-dessous définit une nouvelle collection de paramètres de configuration de conférence, qui sont initialement stockés en mémoire, puis ultérieurement appliqués au site de Redmond. 
  
La première commande utilise l’applet de commande **New-CsConferencingConfiguration** pour créer une collection de paramètres en mémoire stockée dans la variable $x. Le paramètre InMemory spécifie que la collection doit être créée en mémoire au lieu d’être immédiatement appliquée au site Redmond.
  
Une fois la collection créée, la deuxième commande définit la valeur de la propriété Organization sur Litwareinc. 
  
Enfin, la troisième commande utilise l’applet de commande **Set-CsConferencingConfiguration** pour appliquer les nouveaux paramètres au site Redmond :
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Si vous n’appelez pas l’applet de commande **Set-CsConferencingConfiguration**, les nouveaux paramètres ne s’appliquent pas. Ils disparaissent dès que vous mettez fin à votre session nm-winshell-2nd ou supprimez la variable $x.
  

