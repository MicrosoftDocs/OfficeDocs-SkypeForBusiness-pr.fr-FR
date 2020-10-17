---
title: 'Lync Server 2013 : configuration d’AD FS 2,0 pour prendre en charge l’authentification client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d2b713d109a72431e78e966258a84c084523a7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517641"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Configuration d’AD FS 2,0 pour prendre en charge l’authentification client dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-03_

Il existe deux types d’authentification possibles pouvant être configurés pour permettre à AD FS 2,0 de prendre en charge l’authentification à l’aide de cartes à puce :

  - Authentification basée sur les formulaires (FBA)

  - Authentification du client TLS (Transport Layer Security)

À l’aide de l’authentification basée sur les formulaires, vous pouvez développer une page Web qui permet aux utilisateurs de s’authentifier en utilisant leur nom d’utilisateur/mot de passe ou en utilisant leur carte à puce et leur code confidentiel. Cette rubrique se concentre sur la mise en œuvre de l’authentification du client TLS (Transport Layer Security) avec les services ADFS 2,0. Pour plus d’informations sur les types d’authentifications AD FS 2,0, voir AD FS 2,0 : comment modifier le type d’authentification local à [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) .

<div>


**Pour configurer AD FS 2,0 afin de prendre en charge l’authentification client**

1.  Connectez-vous à l’ordinateur AD FS 2,0 à l’aide d’un compte d’administrateur de domaine.

2.  Lancez l’Explorateur Windows.

3.  Accédez à C : \\ Inetpub \\ ADFS \\ ls.

4.  Effectuez une copie de sauvegarde du fichier web.config existant.

5.  Ouvrez le fichier de web.config existant à l’aide du bloc-notes.

6.  Dans la barre de menus, sélectionnez **modifier** , puis **Rechercher**.

7.  Recherchez **\<localAuthenticationTypes\>** .
    
    Notez qu’il existe quatre types d’authentification répertoriés, un par ligne.

8.  Déplacez la ligne contenant le type d’authentification TLSClient en haut de la liste dans la section.

9.  Enregistrez et fermez le fichier web.config.

10. Lancez une invite de commandes avec des privilèges élevés.

11. Redémarrez les services Internet (IIS) en exécutant la commande suivante :
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

