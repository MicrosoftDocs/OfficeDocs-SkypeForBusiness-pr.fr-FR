---
title: 'Lync Server 2013 : désactivation ou réactivation du compte d’utilisateur pour Lync Server'
description: 'Lync Server 2013 : désactivez ou réactivez le compte d’utilisateur pour Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b30d83d7a7f38b84f8e669ac06947eebf4a8545
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568170"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-04-04_

Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur précédemment activé dans Lync Server 2013 sans perdre les paramètres Lync Server que vous avez configurés pour le compte d’utilisateur. Étant donné que vous ne perdez pas les paramètres de compte d’utilisateur Lync Server, vous pouvez réactiver un compte d’utilisateur précédemment activé sans avoir à reconfigurer le compte d’utilisateur.

<div>


> [!WARNING]  
> La simple désactivation d’un compte d’utilisateur dans Active Directory n' <STRONG>empêchera pas</STRONG> un utilisateur de se connecter à ou d’utiliser Lync Server. En effet, Lync utilise l’authentification de certificat qui rationalise le processus d’authentification, et ces certificats clients sont valides pendant 180 jours. Si vous souhaitez arrêter les comptes Active Directory désactivés qui ont été activés pour que Lync ait accès à Lync Server, vous devez utiliser l’applet de commande <STRONG>Disable-Csuser</STRONG> ou utiliser le <STRONG>panneau de configuration Lync Server</STRONG> comme indiqué dans cet article. Une fois que l’utilisateur est désactivé dans Lync et que le magasin central de gestion a été répliqué dans l’environnement, les utilisateurs ne pourront plus se connecter. En outre, les utilisateurs qui sont connectés seront déconnectés.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Pour désactiver ou réactiver un compte d’utilisateur précédemment activé pour Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.

6.  Dans le menu **Action**, effectuez l’une des opérations suivantes :
    
      - Pour désactiver temporairement le compte d’utilisateur pour Lync Server 2013, cliquez sur **désactiver temporairement pour Lync Server**.
    
      - Pour activer le compte d’utilisateur pour Lync Server 2013, cliquez sur **réactiver pour Lync Server**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Utilisation de Windows PowerShell pour désactiver ou réactiver des comptes d’utilisateurs

Les comptes d’utilisateur peuvent être temporairement désactivés, puis réactivés ultérieurement à l’aide de la cmdlet **Set-Csuser** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-disable-a-user-account"></a>Pour désactiver un compte d’utilisateur

  - Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur False ($False). Par exemple :
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>Pour réactiver un compte d’utilisateur

  - Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur True ($True). Par exemple :
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Ajouter et activer un compte d’utilisateur pour Lync Server 2013](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Activation et désactivation des utilisateurs pour Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

