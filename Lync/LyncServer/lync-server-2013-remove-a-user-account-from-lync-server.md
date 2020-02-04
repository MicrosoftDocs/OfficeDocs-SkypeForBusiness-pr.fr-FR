---
title: 'Lync Server 2013 : supprimer un compte d’utilisateur de Lync Server'
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
ms.openlocfilehash: 97ee26fd15eb9df9174fd33cf9a45a6fe49411af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>Supprimer un compte d’utilisateur de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur déjà ajouté dans Lync Server 2013.

<div>


> [!NOTE]  
> La suppression d’un utilisateur entraîne la perte des paramètres que vous avez configurés pour le compte d’utilisateur. Si vous voulez désactiver temporairement un compte d’utilisateur à la place, reportez-vous à la rubrique <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">désactiver ou réactiver un compte d’utilisateur pour Lync Server 2013</A>.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Pour supprimer un compte d’utilisateur à l’aide de Lync Server Management Shell

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité (Sam), adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5.  Dans la table, cliquez sur le compte d’utilisateur que vous voulez supprimer.

6.  Dans le menu **action** , sélectionnez **supprimer de Lync Server**et une boîte de dialogue s’affiche.

7.  Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Suppression de comptes d’utilisateur à l’aide des applets de cmdlet Windows PowerShell

Vous pouvez supprimer des comptes d’utilisateurs à l’aide de l’applet de passe Disable-CsUser. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-remove-a-user-account"></a>Pour supprimer un compte d’utilisateur

  - Pour supprimer un compte d’utilisateur, utilisez l’applet de passe Disable-CsUser. Par exemple :
    
        Disable-CsUser -Identity "Ken Myer"
    
    Après avoir exécuté cette commande, il est impossible de réactiver le compte et ses paramètres précédents. Au lieu de cela, vous devez utiliser l’applet de passe Enable-CsUser pour créer un nouveau compte pour Ken Myer.

</div>

Pour plus d’informations, reportez-vous à la rubrique d’aide de l’applet de la cmdlet [Disable-Csuser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .

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

