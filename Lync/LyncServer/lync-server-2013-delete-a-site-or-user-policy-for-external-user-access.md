---
title: 'Lync Server 2013 : Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes'
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
ms.openlocfilehash: b928fcb1347fdbc89099a5b0dc649deefffa19e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Vous pouvez supprimer n’importe quelle stratégie de site ou d’utilisateur figurant dans le panneau de configuration de Lync Server sur la page de **stratégie d’accès externe** . La suppression de la stratégie globale n’entraîne pas la suppression effective de celle-ci, mais elle permet de rétablir les paramètres par défaut, qui n’incluent pas la prise en charge des options d’accès des utilisateurs externes. Pour plus d’informations sur la réinitialisation de la stratégie globale, voir [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Pour supprimer une stratégie de site ou d’utilisateur pour l’accès des utilisateurs externes

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.

4.  Dans l’onglet **stratégie d’accès externe** , cliquez sur le site ou la stratégie d’utilisateur à supprimer, cliquez sur **modifier**, puis cliquez sur **supprimer**.

5.  Lorsque vous êtes invité à confirmer la suppression, cliquez sur **OK**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Suppression de stratégies de code confidentiel à l’aide d’applets de cmdlet Windows PowerShell

Les stratégies d’accès externe peuvent être supprimées à l’aide de Windows PowerShell et de l’applet de passe Remove-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>Pour supprimer une stratégie d’accès externe spécifique

  - Cette commande supprime la stratégie d’accès externe appliquée au site de Redmond :
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Pour supprimer toutes les stratégies d’accès externe appliquées à l’étendue par utilisateur

  - Cette commande supprime toutes les stratégies d’accès externe configurées pour l’étendue par utilisateur :
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Pour supprimer toutes les stratégies d’accès externes pour lesquelles l’accès des utilisateurs externes est désactivé

  - Cette commande supprime toutes les stratégies d’accès externe dont l’accès à l’utilisateur extérieur a été désactivé :
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

