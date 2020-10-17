---
title: 'Lync Server 2013 : installation des composants de Lync Server Server'
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
ms.openlocfilehash: 9237ed0b60e14383f69ff1e7ef0b0927afe49c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498701"
---
# <a name="install-server-components-for-lync-server-2013"></a>Installer les composants serveur pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-05_

Avant de suivre cette procédure, assurez-vous que vous êtes connecté au serveur avec un compte d’utilisateur de domaine qui est à la fois un administrateur local et un membre du groupe RTCUniversalReadOnlyAdmins dans Active Directory.

L’Assistant Déploiement de Lync Server est utilisé pour installer les composants nécessaires pour chaque rôle Lync Server et pour activer le serveur. Cet article vous guide tout au long de la procédure de déploiement d’un serveur Standard Edition ou d’un serveur frontal dans votre infrastructure Lync.

<div>

## <a name="to-install-lync-server-components"></a>Pour installer les composants Lync Server

1.  Si l’Assistant Déploiement de Lync Server n’est pas en cours d’exécution, démarrez-le sur le serveur sur lequel vous souhaitez installer Lync.

2.  Cliquez sur **installer ou mettre à jour le système Lync Server**.

3.  Dans l’Assistant Déploiement, vérifiez que l' **étape 1 : installer le magasin de configurations local** a une coche verte, ce qui signifie que ce serveur a une copie locale de la banque installée. Si ce n’est pas déjà fait, vous devez installer le magasin de configurations local sur le serveur. Suivez les étapes décrites [dans Install the local Configuration Store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) , puis revenez ici.

4.  Lorsque vous êtes prêt à installer les composants Lync Server 2013 sur votre serveur, cliquez sur **exécuter** à côté de **étape 2 : installer ou supprimer des composants Lync Server**.

5.  Dans la page **configurer les composants Lync Server** , cliquez sur **suivant** pour configurer les composants comme défini dans votre topologie publiée.

6.  La page **exécution de commandes** affiche un résumé des commandes et des informations d’installation à mesure que la configuration a lieu. Une fois cette opération terminée, vous pouvez sélectionner un journal à afficher dans la liste, puis cliquer sur **afficher le journal**.

7.  Lorsque le programme d’installation des composants Lync Server 2013 est terminé et que vous avez examiné les journaux selon vos besoins, cliquez sur **Terminer** pour effectuer cette étape dans l’installation.
    
    <div>
    

    > [!NOTE]  
    > Si vous êtes invité à redémarrer le serveur (ce qui peut se produire si l’expérience de bureau Windows devait être installée), faites-le. Lorsque l’ordinateur est en cours d’exécution, vous devez effectuer les opérations suivantes de nouveau, en commençant à l’étape 3 ci-dessus (exécutez l’étape 2 de l’Assistant Déploiement une fois de plus).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

