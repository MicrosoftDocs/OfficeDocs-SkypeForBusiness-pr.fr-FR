---
title: Créer ou modifier une collection de paramètres de configuration d’cdr dans Skype Entreprise Server
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Résumé : Découvrez l’enregistrement des détails des appels dans Skype Entreprise Server.'
ms.openlocfilehash: 9e77cc7782116f317504cbbee98d0731d69ed5e8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751743"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Créer ou modifier une collection de paramètres de configuration d’cdr dans Skype Entreprise Server
 
**Résumé :** Découvrez l’enregistrement des détails des appels dans Skype Entreprise Server.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de l’entretien.
  
Lorsque vous installez Skype Entreprise Server collection unique et globale de paramètres de configuration d’cdr est créée pour vous. Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site. Chaque fois que ces paramètres d’étendue de site sont utilisés, ils prennent la priorité sur les paramètres globaux. Par exemple, si vous créez des paramètres pour l’étendue du site de Redmond, ces paramètres (au lieu des paramètres globaux) servent alors à gérer l’enregistrement des détails des appels à Redmond.
  
Vous pouvez créer des paramètres de configuration d’Skype Entreprise Server à l’aide du Panneau de configuration ou de l’cmdlet [New-CsCdrConfiguration.](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Vous pouvez utiliser Skype Entreprise Server panneau de configuration ou l’cmdlet [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) pour modifier les paramètres existants. Si vous utilisez Skype Entreprise Server panneau de configuration pour créer ou modifier des paramètres, les options suivantes sont disponibles :
  
|**Paramètre de l’interface utilisateur**|**Paramètre PowerShell**|**Description**|
|:-----|:-----|:-----|
|Nom  <br/> |Identité  <br/> |Identificateur unique pour les paramètres de configuration d’enregistrement des détails des appels créés. Ces paramètres peuvent uniquement être créés au niveau de l’étendue Site.  <br/> |
|Activer la surveillance des enregistrements des détails des appels  <br/> |EnableCDR  <br/> |Indique si l’enregistrement des détails des appels est activé ou non.  <br/> |
|Activer le vidage des enregistrements des détails des appels  <br/> |EnablePurging  <br/> |Indique si les enregistrements des détails des appels doivent être périodiquement supprimés de la base de données d’enregistrements des détails des appels.  <br/> |
|Conserver les enregistrements des détails des appels pendant la durée maximale (jours)  <br/> |KeepCallDetailForDays  <br/> |Indique le nombre de jours pendant lesquels les enregistrements des détails des appels sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. (Notez que le vidage ne se produit que s’il est activé.)  <br/> |
|Conserver les données de signalement d’erreurs pendant la durée maximale (jours)  <br/> |KeepErrorReportForDays  <br/> |Indique le nombre de jours pendant lesquels les rapports d’erreur des détails des appels sont conservés. Tout rapport plus ancien que le nombre de jours spécifié est automatiquement supprimé. Les rapports d’erreur des détails des appels sont des rapports de diagnostic téléchargés par les applications clientes.  <br/> |
   
> [!NOTE]
> Les cmdlets New-CsCdrConfiguration et Set-CsCdrConfiguration comprennent des options supplémentaires qui ne sont pas disponibles dans Skype Entreprise Server panneau de Skype Entreprise Server. Pour plus d’informations, voir les rubriques d’aide [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) et [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour créer des paramètres de configuration cdR à l’aide Skype Entreprise Server panneau de configuration

1. In Skype Entreprise Server Control Panel click **Monitoring and Archiving**.
    
2. Sous **l’onglet Enregistrement des détails des** appels, cliquez sur **Nouveau.**
    
3. Dans la boîte de dialogue **Sélectionner un site**, indiquez le site où les nouveaux paramètres de configuration doivent être créés. Si la boîte de dialogue est vide, cela indique qu’une collection de paramètres de configuration d’enregistrement des détails des appels a déjà été affectée à tous vos sites. Chaque site ne peut recevoir qu’une seule collection. Vous pouvez dans ce cas supprimer puis recréer les paramètres ou modifier simplement les paramètres existants.
    
4. Dans la boîte de dialogue **Nouveau paramètre d’enregistrement des détails des appels (CDR)**, sélectionnez les options voulues, puis cliquez sur **Valider**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour modifier les paramètres de configuration cdR existants à l’aide Skype Entreprise Server panneau de configuration

1. In Skype Entreprise Server Control Panel click **Monitoring and Archiving**.
    
2. Double-cliquez sur la collection de paramètres à modifier, ou sélectionnez la collection, cliquez sur **Modifier**, puis sur **Afficher les détails**. Sachez que vous ne pouvez modifier qu’une seule collection à la fois. Pour apporter les mêmes modifications à plusieurs collections, utilisez l’Skype Entreprise Server Management Shell à la place.
    
3. Dans la boîte de dialogue **Modifier le paramètre de l’enregistrement des détails des appels**, sélectionnez les options voulues, puis cliquez sur **Valider**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de paramètres de configuration d’cdr à l’Windows PowerShell cmdlets

Vous pouvez également créer des paramètres de configuration d’cdr à l’aide de Windows PowerShell et de l’cmdlet **New-CsCdrConfiguration.** Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels

 La commande crée une collection de paramètres de configuration pour l’enregistrement des détails des appels qui s’applique au site Redmond :
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels qui désactivent l’enregistrement des détails des appels

 Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur. Par exemple, pour créer une collection de paramètres de configuration des détails des appels, l’autorisation de la désactivation de l’enregistrement des détails des appels fait appel par défaut à une commande comme celle-ci :
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Pour spécifier plusieurs valeurs de propriétés pendant la création d’une collection de paramètres de configuration d’enregistrement des détails des appels

 Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour conserver les enregistrements des détails des appels pendant 30 jours et les rapports d’erreur 90 jours :
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [New-CsCdrConfiguration.](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)
