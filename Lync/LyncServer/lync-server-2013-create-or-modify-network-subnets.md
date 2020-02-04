---
title: 'Lync Server 2013 : création ou modification de sous-réseaux réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d743e5cdbe8dc7f200175b74f55b1b3d003e769
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Créer ou modifier des sous-réseaux réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Un sous-réseau doit être associé à un site réseau pour vous permettre de déterminer l’emplacement géographique de l’hôte appartenant à ce sous-réseau. Le panneau de configuration de Lync Server vous permet de configurer les sous-réseaux. Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau. Pour plus d’informations sur la suppression de sous-réseaux réseau, voir [Suppression de sous-réseaux réseau dans Lync Server 2013](lync-server-2013-deleting-network-subnets.md).

Dans la plupart des déploiements de Microsoft Lync Server 2013 sur lequel est implémenté le contrôle d’admission des appels, il existe généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Lync Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de cmdlet Windows PowerShell **Import-CSV**. L’utilisation conjointe de ces applets de passe vous permet de lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et de créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples sur la façon de créer des sous-réseaux à partir d’un fichier. csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>Pour créer un sous-réseau du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **sous-réseau**.

4.  Sur la page **sous-réseau** , cliquez sur **nouveau**.

5.  Dans **nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau** . Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0) et doit être la première adresse de la plage d’adresses IP définie par le sous-réseau.

6.  Dans le champ **masque** , entrez une valeur numérique comprise entre 1 et 32.
    
    <div>
    

    > [!NOTE]  
    > Cette valeur correspond au masque de passe à appliquer au sous-réseau qui est créé.

    
    </div>

7.  Dans **ID du site réseau**, sélectionnez le site auquel appartient ce sous-réseau.

8.  Facultatif Tapez une valeur dans le champ **Description** pour fournir davantage d’informations sur ce sous-réseau qui ne peut pas être exprimé par le nom seul.

9.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>Pour modifier un sous-réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **sous-réseau**.

4.  Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier le sous-réseau** , vous pouvez modifier le masque de la page, le site réseau associé ou la description. Si vous modifiez le masque de réinitialisation, n’oubliez pas que l’ID de sous-réseau doit toujours être la première adresse de la plage d’adresses IP définie par le sous-réseau.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer des sous-réseaux réseau dans Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


[À propos des régions réseau, des sites réseau et des sous-réseaux dans Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

