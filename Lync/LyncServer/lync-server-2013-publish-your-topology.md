---
title: 'Lync Server 2013 : Publication de la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bd80b5b3dfdb71a054c7600a06e892f1396f048
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>Publication de la topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Chaque fois que vous utilisez le générateur de topologie pour générer votre topologie, vous devez publier la topologie sur une base de données dans la Banque centrale de gestion pour que les données puissent être utilisées pour le déploiement de Lync Server 2013. Utilisez la procédure suivante pour publier votre topologie.

<div>

## <a name="to-publish-the-topology"></a>Pour publier la topologie

1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans le générateur de topologie, dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync 2013**, puis cliquez sur **topologie de publication**.

3.  Dans la page **Bienvenue** de l’Assistant, cliquez sur **Suivant**.

4.  Dans le **Générateur de topologie a détecté une page CMS Store** , cliquez sur **suivant**.

5.  Dans la page **Créer d’autres bases de données**, cliquez sur **Suivant**.

6.  Lorsque l’état indique la création réussie de la base de données, procédez comme suit :
    
      - Pour afficher le journal, cliquez sur **Afficher le journal**.
    
      - Pour fermer l’Assistant, cliquez sur **Terminer**.
        
        <div>
        

        > [!IMPORTANT]  
        > S’il s’agit d’une nouvelle installation d’un serveur de périphérie ou d’un pool de périphériques, vous devez exporter la configuration de serveur Edge à partir d’un serveur frontal, d’un pool frontal ou d’un serveur Standard Edition Server. Pour exporter la configuration, reportez-vous à la section <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export de votre topologie Lync Server 2013 et copiez-la sur du média externe pour l’installation Edge</A>. Dans le cadre de l’installation et du déploiement, vous allez importer le fichier de configuration à partir du média externe ou du partage réseau via l’Assistant Déploiement de Lync Server.<BR>Une fois les serveurs Edge opérationnels et la base de données du magasin de gestion des configurations locales répliquant le déploiement interne, les mises à jour ultérieures apportées à la configuration de Lync Server 2013 seront publiées et répliquées sur les serveurs de périphérie.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

