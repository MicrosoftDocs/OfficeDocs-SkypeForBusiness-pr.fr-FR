---
title: 'Lync Server 2013 : désactiver ou réactiver un compte d’utilisateur pour Lync Server'
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
ms.openlocfilehash: aea86048fa29e9b6a21aa040093edff3f53ffe27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-04-04_

Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur déjà activé dans Lync Server 2013 sans perdre les paramètres de serveur Lync que vous avez configurés pour le compte d’utilisateur. Étant donné que vous ne perdez pas les paramètres de compte d’utilisateur de Lync Server, vous pouvez réactiver un compte d’utilisateur déjà activé sans avoir à reconfigurer le compte d’utilisateur.

<div>


> [!WARNING]  
> La désactivation d’un compte d’utilisateur dans Active Directory n' <STRONG>empêchera pas</STRONG> un utilisateur de se connecter ou d’utiliser Lync Server. En effet, Lync utilise l’authentification par certificat qui rationalise le processus d’authentification, et ces certificats clients sont valides pour 180 jours. Si vous souhaitez désactiver les comptes Active Directory désactivés qui ont été activés pour Lync et avoir accès à Lync Server, vous devez utiliser l’applet de commande <STRONG>Disable-Csuser</STRONG> , ou utiliser le <STRONG>panneau de configuration de Lync Server</STRONG> comme prévu dans cet article. Lorsque l’utilisateur est désactivé dans Lync et que le magasin de gestion central a été répliqué dans l’environnement, les utilisateurs ne seront plus en mesure de se connecter. De plus, les utilisateurs connectés seront déconnectés.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Pour désactiver ou réactiver un compte d’utilisateur déjà activé pour Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité (Sam), adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5.  Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.

6.  Dans le menu **action** , effectuez l’une des opérations suivantes :
    
      - Pour désactiver temporairement le compte d’utilisateur pour Lync Server 2013, cliquez sur **désactiver temporairement pour Lync Server**.
    
      - Pour activer le compte d’utilisateur pour Lync Server 2013, cliquez sur **réactiver pour Lync Server**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Utilisation de Windows PowerShell pour désactiver ou réactiver les comptes d’utilisateurs

Pour désactiver temporairement les comptes d’utilisateurs, vous pouvez les réactiver ultérieurement à l’aide de l’applet de dialogue **Set-Csuser** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-disable-a-user-account"></a>Pour désactiver un compte d’utilisateur

  - Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur false ($False). Par exemple :
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>Pour réactiver un compte d’utilisateur

  - Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur true ($True). Par exemple :
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .

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

