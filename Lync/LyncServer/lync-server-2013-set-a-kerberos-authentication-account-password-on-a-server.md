---
title: 'Lync Server 2013 : définition d’un mot de passe de compte d’authentification Kerberos sur un serveur'
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
ms.openlocfilehash: eeb9338943d17be1c970b4aa2ffc04d5e2c8cb86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Définir un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-01-16_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Vous devez configurer un mot de passe sur le compte Kerberos pour chaque site disposant de serveurs frontaux, de serveurs Standard Edition et de directeurs. Vous pouvez configurer le mot de passe en exécutant l’applet de commande Windows PowerShell **Set-CsKerberosAccountPassword** sur un serveur du site (par exemple, un serveur frontal). Pour chaque site, vous devez exécuter l’applet de commande **Set-CsKerberosAccountPassword** . L’applet de commande configure Internet Information Services (IIS) pour le service Web, puis définit le mot de passe sur le compte d’ordinateur dans les services de domaine Active Directory. Une autre méthode, basée sur le type de paramètre utilisé dans l’applet de commande, configure IIS sur un serveur tout en utilisant un autre serveur ayant été configuré comme source du mot de passe du compte Kerberos.

Lorsque vous utilisez l’applet de commande **Set-CsKerberosAccountPassword** pour définir un mot de passe, Kerberos définit le mot de passe en tant que chaîne générée de manière aléatoire. Cette applet de commande contacte toutes les instances IIS de tous les sites Lync Server 2013 centraux auxquels ce compte est affecté.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Pour définir un mot de passe de compte d’authentification Kerberos

1.  Ouvrez une session sur un ordinateur du domaine sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez les deux commandes suivantes :
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Par exemple :
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Vous devez spécifier le paramètre Compte d’utilisateur au format Domaine\Utilisateur. Le format Utilisateur@Domaine.extension n’est pas pris en charge pour le référencement des objets Ordinateur créés à des fins d’authentification Kerberos.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Après avoir apporté des modifications à l’authentification Kerberos, telles que l’ajout d’un compte ou la suppression d’un compte, vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

