---
title: 'Lync Server 2013 : configurer les paramètres de parc d’appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee4f12ccf614816e27262f8b393cdc1dac4a7a5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>Configurer les paramètres de parc d’appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Si vous ne voulez pas utiliser les paramètres de parc d’appels par défaut, vous pouvez les personnaliser. Lorsque vous installez l’application de parc d’appels, les paramètres globaux sont configurés par défaut. Vous pouvez modifier les paramètres généraux et définir également des paramètres spécifiques à un site. L’applet de commande **New-CsCpsConfiguration** permet de créer des paramètres spécifiques à un site. L’applet de commande **Set-CsCpsConfiguration** permet de modifier les paramètres existants.

<div>


> [!NOTE]  
> Nous vous recommandons de configurer au moins l’option <STRONG>OnTimeoutURI</STRONG> pour la destination de remplacement à utiliser lorsqu’un appel parqué échoue.



</div>

Les applets de commande **New-CsCpsConfiguration** et **Set-CsCpsConfiguration** permettent de configurer les paramètres suivants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cette option :</th>
<th>Spécifie cet élément :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>Période qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.</p>
<p>La valeur doit être entrée au format hh:mm:ss (heures, minutes, secondes). La valeur minimale est de 10 secondes et la valeur maximale, de 10 minutes. La valeur par défaut est 00:01:30.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>Si une musique est diffusée pour l’appelant pendant le parcage d’un appel.</p>
<p>Les valeurs sont True ou False. La valeur par défaut est True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>Nombre de sonnerie de rappel d’un appel parqué avant qu’il soit transféré vers l’URI de remplacement spécifié pour le paramètre <strong>OnTimeoutURI</strong>. La valeur par défaut est 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>Adresse SIP (Session Initiation Protocol) de l’utilisateur ou groupe Response Group vers laquelle l’appel parqué sans réponse est routé lorsque la valeur <strong>MaxCallPickupAttempts</strong> est atteinte.</p>
<p>La valeur doit être une URI SIP (Session Initiation Protocol) et commencer par la chaîne « sip: ». Par exemple, sip:bob@contoso.com. La valeur par défaut est aucune adresse de transfert.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>Pour configurer les paramètres du parc d’appels

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > L’applet de commande <STRONG>Get-CsSite</STRONG> permet d’identifier le site. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.

    
    </div>
    
    Par exemple :
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Personnaliser le parc d’appels en attente dans Lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  


[Nouveau-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

