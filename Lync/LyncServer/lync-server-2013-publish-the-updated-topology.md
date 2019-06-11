---
title: 'Lync Server 2013 : Publication de la topologie mise à jour'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f3be1443f98444712a66942417e1812181efe7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Publication de la topologie mise à jour dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

Après avoir effectué la mise à jour de votre topologie dans le générateur de topologie, vous devez publier la topologie dans le centre de gestion central avant de pouvoir configurer et utiliser le serveur de chat permanent. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.

<div>

## <a name="to-publish-an-updated-topology"></a>Pour publier une topologie mise à jour

Avant de publier votre topologie, installez les bases de données pour le serveur de chat permanent. Utilisez le générateur de topologie pour installer des bases de données en sélectionnant **action** et **installer la base de données**.

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel sont installés les outils d’administration de Lync Server, connectez-vous à l’aide d’un compte membre du groupe **administrateurs de domaine** et du groupe **RTCUniversalServerAdmins** et disposant du contrôle total. les autorisations (en lecture, en écriture et en modification) sur le magasin de fichiers à utiliser pour le stockage des fichiers du serveur de chat permanent (de sorte que le générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaire requises), ou un compte avec des droits d’utilisateur équivalents.

2.  Démarrer le générateur de topologie. Sélectionnez l’option **Télécharger la topologie à partir du déploiement existant**ou **Ouvrez la topologie à partir d’un fichier local** si vous l’avez enregistrée localement.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **publier la topologie**.

4.  Dans la page **Publier la topologie**, cliquez sur **Suivant**.

5.  Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!IMPORTANT]  
    > Après la publication de la topologie, vous devez configurer la prise en charge du serveur de chat permanent pour pouvoir archiver le contenu.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

