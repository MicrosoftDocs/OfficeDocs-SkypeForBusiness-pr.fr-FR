---
title: Afficher les informations de configuration de l’Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Résumé : Découvrez comment utiliser l’enregistrement des détails des appels dans Skype Entreprise Server.'
ms.openlocfilehash: 058a6538c8486c52fd47354fe4116e339c83a8b9479ec2da214c4f39d8558308
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341879"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Afficher les informations de configuration de l’Skype Entreprise Server
 
**Résumé :** Découvrez comment utiliser l’enregistrement des détails des appels dans Skype Entreprise Server.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.
  
Lorsque vous installez Skype Entreprise Server, une collection unique et globale de paramètres de configuration d’cdr est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Vous pouvez afficher les paramètres de configuration cdR utilisés dans votre organisation à l’aide du Panneau de configuration Skype Entreprise Server ou de l’cmdlet [Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Pour afficher les informations de configuration cdR à l’aide Skype Entreprise Server panneau de configuration

1. In Skype Entreprise Server Control Panel click **Monitoring and Archiving**.
    
2. La liste de tous vos paramètres de configuration d’enregistrement des détails des appels s’affiche sous l’onglet **Enregistrement des détails des appels** ; pour chaque collection de paramètres apparaissent la collection **Nom**, l’indication stipulant si l’enregistrement des détails des appels a été activé ou non (propriété **Enregistrement des détails des appels**) et l’indication stipulant si le vidage a été activé (propriété **Vidage de l’enregistrement des détails des appels**). Pour plus d’informations sur une collection, double-cliquez dessus ou sélectionnez la collection appropriée, cliquez sur **Modifier**, puis sur **Afficher les détails**. Notez que vous pouvez uniquement afficher des informations détaillées pour une seule collection de paramètres de configuration d’enregistrement des détails des appels à la fois.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration cdR à l’aide Windows PowerShell cmdlets

Vous pouvez afficher les paramètres de configuration de l’Windows PowerShell à l’aide Get-CsCdrConfiguration cmdlet. Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, voir l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-view-cdr-configuration-information"></a>Pour afficher les informations de configuration d’enregistrement des détails des appels

- Pour afficher des informations sur tous vos paramètres de configuration d’cdr, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
