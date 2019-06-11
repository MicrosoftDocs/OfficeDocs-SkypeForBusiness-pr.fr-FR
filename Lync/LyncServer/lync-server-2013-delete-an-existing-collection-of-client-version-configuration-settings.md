---
title: Supprimer une collection existante de paramètres de configuration de la version du client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a71df7af1f0a6158cb61e780b44ed4227d32018
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Supprimer une collection existante de paramètres de configuration de la version du client dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Si vous voulez supprimer les paramètres de configuration de client déjà configurés pour un site, vous pouvez supprimer les paramètres dans Lync Server 2013 Control Panel ou Lync Server 2013 Management Shell.

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a>Pour supprimer les paramètres de configuration du client à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .

4.  Sélectionnez le site, cliquez sur **modifier**, sur **supprimer**, puis sur **OK**.

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration de la version du client à l’aide des cmdlets Windows PowerShell

Vous pouvez supprimer des paramètres de configuration de la version du client à l’aide de l’applet de contrôle **Remove-CsClientVersionConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a>Pour supprimer une collection spécifiée de paramètres de configuration de la version du client

  - La commande suivante supprime les paramètres de configuration de la version du client appliqués au site de Redmond:
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration de la version du client appliqués à l’étendue du site

  - Cette commande supprime tous les paramètres de configuration de la version du client configurés pour l’étendue du site:
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a>Pour supprimer tous les paramètres de configuration de la version du client en fonction de la valeur de la propriété DefaultAction

  - Cette commande supprime tous les paramètres de configuration de la version du client pour lesquels l’action par défaut a été définie sur «bloquer»:
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

