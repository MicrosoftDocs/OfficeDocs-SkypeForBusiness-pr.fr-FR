---
title: 'Lync Server 2013 : Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97130b93052c0e14e1e4b4863be8ceea6118db05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-01-16_

Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Vous devez configurer un mot de passe sur le compte Kerberos de chaque site qui comporte des serveurs front-end, Standard Edition Server et Directors. Vous pouvez configurer le mot de passe en exécutant l’applet de cmdlet Windows PowerShell **Set-CsKerberosAccountPassword** sur un serveur du site (par exemple, un serveur frontal). Pour chaque site, vous devez exécuter l’applet de cmdlet **Set-CsKerberosAccountPassword** . L’applet de contrôle configure Internet Information Services (IIS) pour le service de services Web, puis définit le mot de passe sur le compte d’ordinateur dans les services de domaine Active Directory (AD DS). Une autre méthode, en fonction du paramètre utilisé avec l’applet de passe, configure IIS sur un serveur lors de l’utilisation d’un autre serveur configuré comme source du mot de passe du compte Kerberos.

Lorsque vous utilisez l’applet de cmdlet **Set-CsKerberosAccountPassword** pour définir un mot de passe, Kerberos définit le mot de passe sur une chaîne générée de manière aléatoire. Cette applet de cmdlet contacte toutes les instances IIS dans tous les sites centraux Lync Server 2013 auxquels ce compte est attribué.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Pour définir un mot de passe pour un compte d’authentification Kerberos

1.  Ouvrez une session sur n’importe quel ordinateur du domaine sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez les deux commandes suivantes :
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Par exemple :
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Vous devez spécifier le paramètre UserAccount en utilisant le format domaine\utilisateur. Le format User@Domain. extension n’est pas pris en charge pour référencer les objets ordinateur créés à des fins d’authentification Kerberos.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Après avoir apporté des modifications à l’authentification Kerberos (par exemple, ajout d’un compte ou suppression d’un compte), vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes de Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

