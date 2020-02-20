---
title: 'Lync Server 2013 : suppression d’un site ou d’une stratégie utilisateur pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc50d2738329fd1ce9e07406b7b7212394257883
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>Supprimer une stratégie d’utilisateur ou de site pour l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Vous pouvez supprimer n’importe quelle stratégie d’utilisateur ou de site figurant dans le panneau de configuration Lync Server sur la page **stratégie d’accès externe** . La suppression de la stratégie globale ne la supprime pas, mais la rétablit uniquement aux paramètres par défaut, qui ne prennent pas en charge les options d’accès des utilisateurs externes. Pour plus d’informations sur la réinitialisation de la stratégie globale, voir [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Pour supprimer une stratégie d’utilisateur ou de site pour l’accès des utilisateurs externes

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Cliquez sur **accès des utilisateurs externes**, puis sur **stratégie d’accès externe**.

4.  Sous l’onglet **stratégie d’accès externe** , cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur **modifier**, puis cliquez sur **supprimer**.

5.  À l’invite de confirmation de la suppression, cliquez sur **OK**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Suppression de stratégies de code confidentiel à l’aide des applets de commande Windows PowerShell

Les stratégies d’accès externe peuvent être supprimées à l’aide de Windows PowerShell et de l’applet de commande Remove-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>Pour supprimer une stratégie d’accès externe spécifique

  - Cette commande supprime la stratégie d’accès externe appliquée au site Redmond :
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Pour supprimer toutes les stratégies d’accès externe appliquées à l’étendue par utilisateur

  - Cette commande permet de supprimer toutes les stratégies d’accès externe configurées au niveau de l’étendue utilisateur :
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Pour supprimer toutes les stratégies d’accès externe dans lesquelles l’accès des utilisateurs externes est désactivé

  - Cette commande supprime toutes les stratégies d’accès externe dans lesquelles l’accès des utilisateurs extérieurs a été désactivé :
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

