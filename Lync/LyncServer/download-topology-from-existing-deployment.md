---
title: Téléchargement de la topologie à partir d’un déploiement existant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29a8bd95af99b6b79b91f84231120c6981eeedb7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>Téléchargement de la topologie à partir d’un déploiement existant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-29_

Lors de la création d’un pool Lync Server 2013, vous allez utiliser le magasin de gestion central associé à Lync Server 2010. Lorsque vous démarrez le générateur de topologie lors de la première utilisation et des sessions d’édition ultérieures, vous êtes invité à indiquer l’emplacement où vous voulez que le générateur de topologie charge le document de configuration actuel. Dans la mesure où une topologie Lync Server 2010 est déjà définie et qu’elle a établi le magasin central de gestion, vous devez choisir de télécharger une topologie à partir d’un déploiement existant. Le générateur de topologie lira la base de données et récupérera la définition actuelle.

**Pour télécharger une topologie à partir d’un déploiement existant**

1.  Ouvrez l' **Assistant Déploiement de Lync Server**.

2.  Dans la page **Lync Server 2013 – Assistant Déploiement** , cliquez sur **installer les outils d’administration**.

3.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013** , puis sur **Générateur de topologie de Lync Server**.

4.  Sélectionnez **Télécharger la topologie à partir du déploiement existant**.
    
    ![Paramètres du générateur de topologie de l’Assistant Déploiement](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Paramètres du générateur de topologie de l’Assistant Déploiement")

5.  Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier default. tbxml.

6.  Développez le nœud Lync Server, comme illustré, pour révéler les différents rôles serveur du déploiement.
    
    ![Propriétés générales du rôle serveur du générateur de topologie](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propriétés générales du rôle serveur du générateur de topologie")

</div>

<span> </span>

</div>

</div>

</div>

