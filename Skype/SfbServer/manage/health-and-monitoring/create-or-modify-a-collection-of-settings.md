---
title: Création ou modification d’une collection de paramètres de configuration de l’enregistrement des détails des appels dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Résumé : Découvrez les détails de l’appel d’enregistrement (CDR) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 9861c3e2fba0f601e47e093a664999052d128f95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server-2015"></a>Création ou modification d’une collection de paramètres de configuration de l’enregistrement des détails des appels dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur les détails de l’appel d’enregistrement (CDR) dans Skype pour Business Server 2015.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de l’entretien.
  
Lorsque vous installez Skype pour Business Server 2015 unique, une collection globale CDR de paramètres de configuration est créée pour vous. Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site. Chaque fois que ces paramètres d’étendue de site sont utilisés, ils prennent la priorité sur les paramètres globaux. Par exemple, si vous créez des paramètres pour l’étendue du site de Redmond, ces paramètres (au lieu des paramètres globaux) servent alors à gérer l’enregistrement des détails des appels à Redmond.
  
Vous pouvez créer des paramètres de configuration de CD-r à l’aide soit Skype pour Business Server du Panneau de configuration ou l’applet de commande [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) . Vous pouvez utiliser Skype pour Business Server du Panneau de configuration ou l’applet de commande [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) pour modifier les paramètres existants. Si vous utilisez Skype pour le panneau de configuration de Business Server permet de créer ou de modifier les paramètres, les options suivantes seront disponibles :
  
|**Définition de l’interface utilisateur**|**Paramètre de PowerShell**|**Description**|
|:-----|:-----|:-----|
|Nom  <br/> |Identity  <br/> |Identificateur unique pour les paramètres de configuration d’enregistrement des détails des appels créés. Ces paramètres peuvent uniquement être créés au niveau de l’étendue Site.  <br/> |
|Activer la surveillance des enregistrements des détails des appels  <br/> |EnableCDR  <br/> |Indique si l’enregistrement des détails des appels est activé ou non.  <br/> |
|Activer le vidage des enregistrements des détails des appels  <br/> |EnablePurging  <br/> |Indique si les enregistrements des détails des appels doivent être périodiquement supprimés de la base de données d’enregistrements des détails des appels.  <br/> |
|Conserver les enregistrements des détails des appels pendant la durée maximale (jours)  <br/> |KeepCallDetailForDays  <br/> |Indique le nombre de jours pendant lesquels les enregistrements des détails des appels sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. (Notez que le vidage ne se produit que s’il est activé.)  <br/> |
|Conserver les données de signalement d’erreurs pendant la durée maximale (jours)  <br/> |KeepErrorReportForDays  <br/> |Indique le nombre de jours pendant lesquels les rapports d’erreur des détails des appels sont conservés. Tout rapport plus ancien que le nombre de jours spécifié est automatiquement supprimé. Les rapports d’erreur des détails des appels sont des rapports de diagnostic téléchargés par les applications clientes.  <br/> |
   
> [!NOTE]
> Les applets de commande New-CsCdrConfiguration et CsCdrConfiguration ensemble comprennent des options supplémentaires n’est pas disponibles dans Skype Business Server du Panneau de configuration. Consultez le [Nouveau-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) et les rubriques d’aide de [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) pour plus d’informations.
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour créer des paramètres de configuration de CD-r pour le panneau de configuration de Business Server à l’aide de Skype

1. Dans Skype pour le panneau de configuration de Business Server, cliquez sur **surveillance et archivage**.
    
2. Sous l’onglet **Appel d’enregistrement de détail** , cliquez sur **Nouveau**.
    
3. Dans la boîte de dialogue **Sélectionner un site**, indiquez le site où les nouveaux paramètres de configuration doivent être créés. Si la boîte de dialogue est vide, cela indique qu’une collection de paramètres de configuration d’enregistrement des détails des appels a déjà été affectée à tous vos sites. Chaque site ne peut recevoir qu’une seule collection. Vous pouvez dans ce cas supprimer puis recréer les paramètres ou modifier simplement les paramètres existants.
    
4. Dans la boîte de dialogue **Nouveau paramètre d’enregistrement des détails des appels (CDR)**, sélectionnez les options voulues, puis cliquez sur **Valider**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour modifier les paramètres de configuration de CDR existants pour le panneau de configuration de Business Server à l’aide de Skype

1. Dans Skype pour le panneau de configuration de Business Server, cliquez sur **surveillance et archivage**.
    
2. Double-cliquez sur la collection de paramètres à modifier, ou sélectionnez la collection, cliquez sur **Modifier**, puis sur **Afficher les détails**. Sachez que vous ne pouvez modifier qu’une seule collection à la fois. Pour apporter les mêmes modifications à plusieurs collections, utilisez plutôt le Skype pour Business Server Management Shell.
    
3. Dans la boîte de dialogue **Modifier le paramètre de l’enregistrement des détails des appels**, sélectionnez les options voulues, puis cliquez sur **Valider**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de paramètres de configuration de CD-r à l’aide des applets de commande Windows PowerShell

Vous pouvez créer la configuration CDR paramètres peuvent également être créés à l’aide de Windows PowerShell et l’applet de commande **New-CsCdrConfiguration** . Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels

 La commande crée une collection de paramètres de configuration pour l’enregistrement des détails des appels qui s’applique au site Redmond :
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels qui désactivent l’enregistrement des détails des appels

 Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur. Par exemple, pour créer une collection de paramètres de configuration des détails des appels, l’autorisation de la désactivation de l’enregistrement des détails des appels fait appel par défaut à une commande comme celle-ci :
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Pour spécifier plusieurs valeurs de propriétés pendant la création d’une collection de paramètres de configuration d’enregistrement des détails des appels

 Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour conserver les enregistrements des détails des appels pendant 30 jours et les rapports d’erreur 90 jours :
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) .
  

