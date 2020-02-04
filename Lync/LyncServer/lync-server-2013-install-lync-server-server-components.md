---
title: 'Lync Server 2013 : Installation des composants serveur Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f039f9363469663410f08f078a3b7e17a170075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Installation des composants serveur pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-05_

Avant d’effectuer cette procédure, vérifiez que vous êtes connecté au serveur à l’aide d’un compte d’utilisateur de domaine qui est un administrateur local et un membre du groupe RTCUniversalReadOnlyAdmins dans Active Directory.

L’Assistant Déploiement de Lync Server est utilisé pour installer les composants nécessaires pour chaque rôle serveur Lync et pour activer le serveur. Cet article vous guide dans la procédure de déploiement d’un serveur Standard Edition Server ou d’un serveur frontal dans votre infrastructure Lync.

<div>

## <a name="to-install-lync-server-components"></a>Pour installer les composants serveur Lync

1.  Si l’Assistant Déploiement de Lync Server n’est pas en cours d’exécution, démarrez-le sur le serveur sur lequel vous voulez installer Lync.

2.  Cliquez sur **installer ou mettre à jour le système de Lync Server**.

3.  Dans l’Assistant Déploiement, confirmez que l' **étape 1 : installer le magasin de configuration local** est une coche verte, ce qui signifie que ce serveur possède une copie locale du Store correctement installée. Si ce n’est pas le cas, vous devez installer le magasin de configuration local sur le serveur. Suivez les étapes décrites dans [installer le magasin de configuration local dans Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) , puis revenez ici.

4.  Lorsque vous êtes prêt à installer les composants Lync Server 2013 sur votre serveur, cliquez sur **exécuter** en regard de l' **étape 2 : configurer ou supprimer les composants Lync Server**.

5.  Sur la page **configurer les composants Lync Server** , cliquez sur **suivant** pour configurer les composants comme définis dans votre topologie publiée.

6.  La page de **commandes en cours d’exécution** affiche un récapitulatif des commandes et des informations d’installation lorsque la configuration est effectuée. Une fois l’opération terminée, vous pouvez sélectionner un journal à afficher dans la liste, puis cliquer sur **Afficher le journal**.

7.  Lorsque l’installation des composants Lync Server 2013 est terminée et que vous avez examiné les journaux le cas échéant, cliquez sur **Terminer** pour achever cette étape de l’installation.
    
    <div>
    

    > [!NOTE]  
    > Si vous êtes invité à redémarrer le serveur (ce qui peut se produire si l’expérience de bureau Windows est nécessaire), faites-le. Lorsque l’ordinateur est restauré et en cours d’exécution, vous devez effectuer ces étapes à nouveau, en commençant à l’étape 3 ci-dessus (exécutez l’étape 2 de l’Assistant Déploiement une fois).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

