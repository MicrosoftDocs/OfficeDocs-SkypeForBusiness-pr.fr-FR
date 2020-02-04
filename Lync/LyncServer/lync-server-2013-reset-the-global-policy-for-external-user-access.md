---
title: 'Lync Server 2013 : Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971239018f3a8e1bcc92c036f50ed36616256ac7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Vous ne pouvez pas supprimer complètement une stratégie globale. L’utilisation de l’option **supprimer** dans la stratégie globale rétablit uniquement les paramètres par défaut de la stratégie globale, qui ne prennent pas en charge les options d’accès des utilisateurs externes.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Pour rétablir les paramètres par défaut de la stratégie globale

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.

4.  Dans l’onglet **stratégie d’accès externe** , cliquez sur politique globale, cliquez sur **modifier**, puis cliquez sur **supprimer**.

5.  Lorsque vous êtes invité à confirmer la suppression, cliquez sur **OK**. Un message s’affiche en haut de la page vous informant que la stratégie globale a été réinitialisée.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Réinitialisation de la stratégie d’accès externe globale à l’aide des cmdlets Windows PowerShell

La stratégie d’accès externe globale peut être réinitialisée à l’aide de Windows PowerShell et de l’applet de passe Remove-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-reset-the-global-external-access-policy"></a>Pour réinitialiser la stratégie d’accès externe globale

  - Cette commande réinitialise la stratégie globale d’accès externe :
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

