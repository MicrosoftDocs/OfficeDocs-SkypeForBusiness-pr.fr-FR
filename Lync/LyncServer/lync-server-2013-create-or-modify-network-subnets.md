---
title: 'Lync Server 2013 : création ou modification de sous-réseaux'
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
ms.openlocfilehash: b9fa570d54a4c65c5f69782a57b4074043a26306
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Création ou modification de sous-réseaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Un sous-réseau de réseau doit être associé à un site réseau afin de déterminer l’emplacement géographique de l’hôte appartenant à ce sous-réseau. Vous pouvez utiliser le panneau de configuration Lync Server pour configurer des sous-réseaux. Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau. Pour plus d’informations sur la suppression des sous-réseaux réseau, consultez [la rubrique Suppression de sous-réseaux réseau dans Lync Server 2013](lync-server-2013-deleting-network-subnets.md).

Dans la plupart des déploiements de Microsoft Lync Server 2013 où le contrôle d’admission des appels (CAC) est implémenté, il y aura généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Lync Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** en association avec l’applet de commande Windows PowerShell **Import-CSV**. En utilisant ces cmdlets ensemble, vous pouvez lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples de création de sous-réseaux à partir d’un fichier. csv, consultez la rubrique [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>Pour créer un sous-réseau de réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.

4.  Dans la page **Sous-réseau**, cliquez sur **Nouveau**.

5.  Dans **Nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau**. Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0), qui doit être la première adresse dans la plage d’adresses IP définie par le sous-réseau.

6.  Dans le champ **Masque**, entrez une valeur numérique comprise entre 1 et 32.
    
    <div>
    

    > [!NOTE]  
    > Cette valeur est le masque de bits à appliquer au sous-réseau en cours de création.

    
    </div>

7.  Dans le champ **ID de site réseau**, sélectionnez le site auquel ce sous-réseau appartient.

8.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce sous-réseau, car son nom ne suffit pas à le décrire.

9.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>Pour modifier un sous-réseau de réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.

4.  Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le sous-réseau**, vous pouvez modifier le masque de bits, le site réseau associé ou la description du sous-réseau. Si vous modifiez le masque de bits, n’oubliez pas que l’ID du sous-réseau doit toujours être la première adresse dans la plage d’adresses IP définie par le sous-réseau.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Suppression de sous-réseaux réseau dans Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


[À propos des régions réseau, des sites et des sous-réseaux dans Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  


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

