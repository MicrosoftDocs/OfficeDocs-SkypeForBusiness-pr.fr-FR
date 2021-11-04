---
title: Gérer les paramètres de configuration du serveur de conférence dans Skype Entreprise Server
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Résumé : Découvrez comment gérer les paramètres de configuration du serveur de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 14fed927e18d291cf17a5c00ee82dac7ef80a6d1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773704"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Gérer les paramètres de configuration du serveur de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer les paramètres de configuration du serveur de conférence dans Skype Entreprise Server.
  
Cette rubrique décrit comment gérer les paramètres de configuration de conférence. Pour plus d’informations sur la façon de planifier et de déployer la conférence, voir [Plan for conferencing in Skype Entreprise Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Les paramètres de configuration de conférence déterminent des éléments tels que la taille maximale autorisée pour le contenu et les handouts de réunion. quantité maximale de bande passante pour le service de conférence de partage d’application ; limites de stockage et périodes d’expiration ; URL pour les téléchargements internes et externes du client pris en charge ; pointeurs vers des URL internes et externes où les utilisateurs peuvent obtenir de l’aide et des ressources de conférence ; et les ports utilisés pour le partage d’application, l’audio client, les transferts de fichiers et le trafic multimédia. Ces paramètres vous permettent de gérer les serveurs eux-mêmes. Ces paramètres peuvent être définies à l’aide Skype Entreprise Server Management Shell.
  
Lorsque vous installez Skype Entreprise Server, le système vous fournit une collection unique de paramètres de configuration de conférence (la collection globale). Si vous souhaitez créer des paramètres personnalisés pour un site ou un service, utilisez l’applet de commande **New-CsConferencingConfiguration**. Notez que les nouveaux paramètres ne peuvent être appliqués qu’au niveau de l’étendue Site ou Service . Vous ne pouvez pas créer une collection globale de paramètres de configuration de conférence, mais vous pouvez modifier la collection globale à l’aide de **l';set-CsConferencingConfiguration.** En outre, aucun site ou service ne peut héberger plus d’une collection de paramètres. Si vous essayez de créer de nouveaux paramètres pour le site Redmond et que le site Redmond héberge déjà une collection de paramètres de configuration de conférence, votre commande échouera.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gérer les paramètres de configuration de conférence à l’aide Skype Entreprise Server Management Shell

Pour gérer les paramètres de configuration de conférence à l’aide Skype Entreprise Server Management Shell, utilisez les cmdlets suivantes :
  
**Paramètres de configuration de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Retourne des informations sur les paramètres de configuration de conférence pour votre organisation.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de conférence.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Supprime la collection spécifiée de paramètres de configuration de conférence.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifie une collection existante de paramètres de configuration de conférence.  <br/> |
   
La commande suivante crée une collection de paramètres de configuration de conférence pour le site Redmond (site:Redmond). Dans cet exemple, un paramètre supplémentaire est inclus (Organization) qui est utilisé pour définir la valeur de la propriété Organization sur Litwareinc : 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Notez que vous ne pouvez avoir qu’une seule collection de ce type par site, donc cette commande échouerait si le site redmond possède déjà une collection de paramètres de configuration de conférence. 
  
L’exemple suivant définit une nouvelle collection de paramètres de configuration de conférence, qui sont stockés initialement en mémoire, puis appliqués ultérieurement au site redmond. 
  
La première commande utilise l';cmdlet **New-CsConferencingConfiguration** pour créer une collection de paramètres en mémoire stockée dans la variable $x. Le paramètre InMemory spécifie que la collection doit être créée en mémoire plutôt que immédiatement appliquée au site redmond.
  
Une fois la collection créée, la deuxième commande définit la valeur de la propriété Organization sur Litwareinc. 
  
Enfin, la troisième commande utilise l';cmdlet **Set-CsConferencingConfiguration** pour appliquer les nouveaux paramètres au site Redmond :
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Si vous n’appelez pas l’cmdlet **Set-CsConferencingConfiguration,** les nouveaux paramètres ne prennent jamais effet. Au lieu de cela, ils disparaîtront dès que vous mettrez fin à votre session Windows PowerShell ou supprimez la variable $x.
