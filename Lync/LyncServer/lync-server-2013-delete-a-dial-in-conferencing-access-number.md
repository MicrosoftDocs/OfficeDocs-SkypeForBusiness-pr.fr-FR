---
title: 'Lync Server 2013 : suppression d’un numéro d’accès à une conférence rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f24565056aac396afd78fb944ae97feec37c905f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Suppression d’un numéro d’accès à une conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Procédez comme suit pour supprimer un numéro d’accès de conférence rendez-vous.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>Pour supprimer un numéro d’accès à une conférence rendez-vous

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **numéro d’accès entrant**.

4.  Sur la page, cliquez sur le numéro d’accès que vous souhaitez supprimer dans la liste, cliquez sur **modifier**, puis sur **supprimer**.

5.  Cliquez sur **OK**.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Suppression des numéros d’accès aux conférences rendez-vous à l’aide des applets de commande Windows PowerShell

Les numéros d’accès aux conférences rendez-vous peuvent être supprimés à l’aide de Windows PowerShell et de l’applet de commande **Remove-applet csdialinconferencingaccessnumber** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>Pour supprimer un numéro d’accès à une conférence rendez-vous spécifique

  - Cette commande supprime le numéro d’accès à la Conférence rendez-vous avec l’identité sip :RedmondDialInAccess@litwareinc.com :
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>Pour supprimer tous les numéros d’accès de conférence rendez-vous affectés à une région spécifique

  - Cette commande supprime tous les numéros d’accès de conférence rendez-vous associés à la région Nord-Ouest :
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>Pour supprimer les numéros d’accès de conférence rendez-vous en fonction de la langue principale

  - Cette commande supprime tous les numéros d’accès aux conférences rendez-vous où l’italien est la langue principale :
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-applet csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

