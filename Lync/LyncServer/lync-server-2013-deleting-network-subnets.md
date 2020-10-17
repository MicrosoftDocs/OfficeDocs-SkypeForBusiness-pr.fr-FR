---
title: 'Lync Server 2013 : suppression de sous-réseaux réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 013de3ae58424473aa42aee767982fd84a9d651e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504271"
---
# <a name="deleting-network-subnets-in-lync-server-2013"></a>Suppression de sous-réseaux réseau dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

La procédure suivante vous permet de supprimer un sous-réseau. Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau. Pour plus d’informations sur la création ou la modification de sous-réseaux réseau, voir [créer ou modifier des sous-réseaux dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

Dans la plupart des déploiements de Microsoft Lync Server 2013 où le contrôle d’admission des appels (CAC) est implémenté, il y aura généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Lync Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** en association avec l’applet de commande Windows PowerShell **Import-CSV**. En utilisant ces cmdlets ensemble, vous pouvez lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples de création de sous-réseaux à partir d’un fichier. csv, consultez la rubrique [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-delete-a-network-subnet"></a>Pour supprimer un sous-réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.

4.  Dans la page **Sous-réseau**, cliquez sur le sous-réseau à supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sous-réseaux à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez les différents sous-réseaux à supprimer. Pour sélectionner la totalité des sous-réseaux, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.

    
    </div>

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification de sous-réseaux dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

