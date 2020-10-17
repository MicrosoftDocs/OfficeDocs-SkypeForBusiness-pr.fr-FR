---
title: 'Lync Server 2013 : création d’un compte d’authentification Kerberos'
description: 'Lync Server 2013 : créez un compte d’authentification Kerberos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f8e87a8ffcc95af4a44e516ac4e1f4d635d737
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542130"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Créer un compte d’authentification Kerberos dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-01-02_

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe Admins du domaine.

Vous pouvez créer des comptes d’authentification Kerberos pour chaque site, ou vous pouvez créer un seul compte d’authentification Kerberos et l’utiliser pour tous les sites. Vous utilisez les applets de commande Windows PowerShell pour créer et gérer les comptes, y compris l’identification des comptes affectés à chaque site. Le générateur de topologie et le panneau de configuration Lync Server 2013 n’affichent pas les comptes d’authentification Kerberos. Suivez la procédure ci-après pour créer un ou plusieurs comptes d’utilisateur pour l’authentification Kerberos.

<div>

## <a name="to-create-a-kerberos-account"></a>Pour créer un compte Kerberos

1.  En tant que membre du groupe administrateurs du domaine, ouvrez une session sur un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande , exécutez la commande suivante :
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Par exemple :
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Vérifiez que l’objet Ordinateur a été créé en ouvrant Utilisateurs et ordinateurs Active Directory, développez le conteneur **Utilisateurs**, puis vérifiez que l’objet Ordinateur du compte d’utilisateur se trouve dans le conteneur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

