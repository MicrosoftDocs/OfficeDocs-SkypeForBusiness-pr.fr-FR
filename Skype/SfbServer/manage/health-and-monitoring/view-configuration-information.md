---
title: Afficher les informations de configuration de CDR dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Résumé: Découvrez comment utiliser l’enregistrement des détails des appels (CDR) dans Skype entreprise Server.'
ms.openlocfilehash: e0aed0c26672b83cb223ba763eb6224025d68118
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279647"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Afficher les informations de configuration de CDR dans Skype entreprise Server
 
**Résumé:** Découvrez comment utiliser l’enregistrement des détails des appels dans Skype entreprise Server.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.
  
Lorsque vous installez Skype entreprise Server, une collection globale unique de paramètres de configuration de CDR est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Vous pouvez afficher les paramètres de configuration de CDR utilisés au sein de votre organisation à l’aide du panneau de configuration Skype entreprise Server ou de l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Pour afficher les informations de configuration de CDR en utilisant le panneau de configuration Skype entreprise Server

1. Dans le panneau de configuration Skype entreprise Server, cliquez sur **surveillance et archivage**.
    
2. La liste de tous vos paramètres de configuration d’enregistrement des détails des appels s’affiche sous l’onglet **Enregistrement des détails des appels** ; pour chaque collection de paramètres apparaissent la collection **Nom**, l’indication stipulant si l’enregistrement des détails des appels a été activé ou non (propriété **Enregistrement des détails des appels**) et l’indication stipulant si le vidage a été activé (propriété **Vidage de l’enregistrement des détails des appels**). Pour plus d’informations sur une collection, double-cliquez dessus ou sélectionnez la collection appropriée, cliquez sur **Modifier**, puis sur **Afficher les détails**. Notez que vous pouvez uniquement afficher des informations détaillées pour une seule collection de paramètres de configuration d’enregistrement des détails des appels à la fois.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de CDR à l’aide des cmdlets Windows PowerShell

Vous pouvez afficher les paramètres de configuration de CDR à l’aide de Windows PowerShell et de l’applet de cmdlet Get-CsCdrConfiguration. Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [«démarrage rapide: gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.
  
### <a name="to-view-cdr-configuration-information"></a>Pour afficher les informations de configuration d’enregistrement des détails des appels

- Pour afficher des informations sur les paramètres de configuration de votre CDR, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:
    
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

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

