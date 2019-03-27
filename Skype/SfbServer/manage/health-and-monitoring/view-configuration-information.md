---
title: Informations de configuration d’affichage des détails des appels dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Résumé : Découvrez comment utiliser les appels d’enregistrement des détails dans Skype pour Business Server.'
ms.openlocfilehash: edf3f719ed3d859ff6d7a6c4fcebbf22356277d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896727"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Informations de configuration d’affichage des détails des appels dans Skype pour Business Server
 
**Résumé :** Découvrez comment utiliser les appels d’enregistrement des détails dans Skype pour Business Server.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.
  
Lorsque vous installez Skype pour Business Server, une seule collection globale des paramètres de configuration CDR est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Vous pouvez afficher les paramètres de configuration CDR utilisés dans votre organisation à l’aide de Skype pour le panneau de configuration serveur Business ou l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Pour afficher les informations de configuration des détails des appels à l’aide de Skype pour Business Server Control Panel

1. Dans Skype pour Business Server le panneau de configuration, cliquez sur **surveillance et archivage**.
    
2. La liste de tous vos paramètres de configuration d’enregistrement des détails des appels s’affiche sous l’onglet **Enregistrement des détails des appels** ; pour chaque collection de paramètres apparaissent la collection **Nom**, l’indication stipulant si l’enregistrement des détails des appels a été activé ou non (propriété **Enregistrement des détails des appels**) et l’indication stipulant si le vidage a été activé (propriété **Vidage de l’enregistrement des détails des appels**). Pour plus d’informations sur une collection, double-cliquez dessus ou sélectionnez la collection appropriée, cliquez sur **Modifier**, puis sur **Afficher les détails**. Notez que vous pouvez uniquement afficher des informations détaillées pour une seule collection de paramètres de configuration d’enregistrement des détails des appels à la fois.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration des détails des appels à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les paramètres de configuration des détails des appels à l’aide de Windows PowerShell et l’applet de commande Get-CsCdrConfiguration. Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Pour afficher les informations de configuration d’enregistrement des détails des appels

- Pour afficher des informations sur tous vos paramètres de configuration CDR, tapez la commande suivante dans le Skype pour Business Server Management Shell et appuyez sur ENTRÉE :
    
  ```
  Get-CsCdrConfiguration
  ```

    Vous obtiendrez des indications semblables à ceci :
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

