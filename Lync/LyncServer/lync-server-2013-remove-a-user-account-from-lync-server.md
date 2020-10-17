---
title: 'Lync Server 2013 : suppression d’un compte d’utilisateur de Lync Server'
description: 'Lync Server 2013 : supprimez un compte d’utilisateur de Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201eb8a7ba620792b92e2c7983890047c249ce86
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555750"
---
# <a name="remove-a-user-account-from-lync-server-2013"></a>Supprimer un compte d’utilisateur de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur ajouté précédemment dans Lync Server 2013.

<div>


> [!NOTE]  
> La suppression d’un utilisateur entraînera la perte de tous les paramètres associés au compte d’utilisateur. Si vous souhaitez désactiver temporairement un compte d’utilisateur, reportez-vous à la rubrique désactiver ou réactiver le <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">compte d’utilisateur pour Lync Server 2013</A>.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Pour supprimer un compte d’utilisateur à l’aide de Lync Server Management Shell

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez supprimer.

6.  Dans le menu **Action**, sélectionnez **Supprimer de Lync Server** et une boîte de dialogue apparaît.

7.  Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Suppression de comptes d’utilisateur à l’aide d’applets de commande Windows PowerShell

Vous pouvez supprimer des comptes d’utilisateurs à l’aide de l’applet de commande Disable-CsUser. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-user-account"></a>Pour supprimer un compte d’utilisateur

  - Pour supprimer un compte d’utilisateur, utilisez l’applet de commande Disable-CsUser. Par exemple :
    
        Disable-CsUser -Identity "Ken Myer"
    
    Une fois cette commande exécutée, il n’y a aucun moyen de réactiver le compte et ses anciens paramètres. En revanche, vous pouvez utiliser l’applet de commande Enable-CsUser pour créer un tout nouveau compte pour Ken Myer.

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Disable-Csuser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Activation et désactivation des utilisateurs pour Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

