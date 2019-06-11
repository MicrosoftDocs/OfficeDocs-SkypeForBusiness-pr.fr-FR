---
title: 'Lync Server 2013: suppression de sous-réseaux réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93806d3e9d5f0cb7f004a90d6f461b363aff65f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Supprimer des sous-réseaux réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Vous pouvez utiliser la procédure suivante pour supprimer un sous-réseau. Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau. Pour plus d’informations sur la création et la modification de sous-réseaux réseau, voir [créer ou modifier des sous-réseaux dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

Dans la plupart des déploiements de Microsoft Lync Server 2013 sur lequel est implémenté le contrôle d’admission des appels, il existe généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Lync Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de cmdlet Windows PowerShell **Import-CSV**. L’utilisation conjointe de ces applets de passe vous permet de lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et de créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples sur la façon de créer des sous-réseaux à partir d’un fichier. csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-delete-a-network-subnet"></a>Pour supprimer un sous-réseau du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **sous-réseau**.

4.  Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous voulez supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sous-réseaux à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs sous-réseaux tout en maintenant la touche CTRL enfoncée. Pour sélectionner tous les sous-réseaux, cliquez sur <STRONG>tout sélectionner</STRONG> dans le menu <STRONG>Edition</STRONG> .

    
    </div>

5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer ou modifier des sous-réseaux réseau dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

