---
title: 'Lync Server 2013 : afficher les informations de configuration de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13bbc63d65786823ae49895358216a903878192
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a>Afficher les informations de configuration de CDR dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale unique de paramètres de configuration de CDR est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Vous pouvez afficher les paramètres de configuration de CDR utilisés au sein de votre organisation à l’aide du panneau de configuration de Lync Server ou de l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a>Pour afficher les informations de configuration de CDR en utilisant le panneau de configuration de Lync Server

1.  Dans le panneau de configuration de Lync Server, cliquez sur **surveillance et archivage**.

2.  La liste de tous vos paramètres de configuration d’enregistrement des détails des appels s’affiche sous l’onglet **Enregistrement des détails des appels** ; pour chaque collection de paramètres apparaissent la collection **Nom**, l’indication stipulant si l’enregistrement des détails des appels a été activé ou non (propriété **Enregistrement des détails des appels**) et l’indication stipulant si le vidage a été activé (propriété **Vidage de l’enregistrement des détails des appels**). Pour plus d’informations sur une collection, double-cliquez dessus ou sélectionnez la collection appropriée, cliquez sur **Modifier**, puis sur **Afficher les détails**. Notez que vous pouvez uniquement afficher des informations détaillées pour une seule collection de paramètres de configuration d’enregistrement des détails des appels à la fois.

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de CDR à l’aide des cmdlets Windows PowerShell

Vous pouvez afficher les paramètres de configuration de CDR à l’aide de Windows PowerShell et de l’applet de cmdlet Get-CsCdrConfiguration. Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-view-cdr-configuration-information"></a>Pour afficher les informations de configuration d’enregistrement des détails des appels

  - Pour afficher des informations sur les paramètres de configuration de votre CDR, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsCdrConfiguration
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

