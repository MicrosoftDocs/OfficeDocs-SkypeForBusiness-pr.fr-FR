---
title: 'Lync Server 2013 : configuration d’AD FS 2,0 pour prendre en charge l’authentification du client'
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
ms.openlocfilehash: c7fe9587e85ad300a212e4a8199fa4a8a48d1877
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Configuration de la 2,0 AD FS pour prendre en charge l’authentification client dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-03_

Deux types d’authentifications peuvent être configurés pour permettre à AD FS 2.0 de prendre en charge l’authentification à l’aide de cartes à puce :

  - Authentification basée sur les formulaires

  - Authentification de client TLS (Transport Layer Security)

L’authentification basée sur les formulaires permet de développer une page web permettant aux utilisateurs de s’authentifier à l’aide de leur nom d’utilisateur et de leur mot de passe ou de leur carte à puce et de leur code confidentiel. Cette rubrique décrit la mise en œuvre de l’authentification de client TLS (Transport Layer Security) avec AD FS 2.0. Pour plus d’informations sur les types d’authentifications 2,0 d’AD FS, voir AD FS 2,0 : Comment changer le [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)type d’authentification locale à.

<div>


**Pour configurer AD FS 2.0 pour prendre en charge l’authentification du client**

1.  Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.

2.  Lancez l’Explorateur Windows.

3.  Naviguez jusqu’à\\C\\:\\Inetpub adfs ls

4.  Effectuez une copie de sauvegarde du fichier web.config existant.

5.  Ouvrez le fichier web.config existant à l’aide du Bloc-notes.

6.  Dans la barre de menus, sélectionnez **Edition**, puis **Rechercher**.

7.  Recherchez ** \<localAuthenticationTypes\>**.
    
    Quatre types d’authentification s’affichent (un par ligne).

8.  Déplacez la ligne contenant le type d’authentification TLSClient au début de la liste dans la section.

9.  Enregistrez et fermez le fichier web.config.

10. Lancez une invite de commandes avec des droits élevés.

11. Redémarrez IIS en exécutant la commande suivante :
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

