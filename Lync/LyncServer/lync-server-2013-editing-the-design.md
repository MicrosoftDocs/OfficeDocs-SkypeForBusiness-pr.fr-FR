---
title: 'Lync Server 2013 : modification de la conception'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f6fa93dbb7ab1ad33b8972b8f09a025dec58c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>Modification de la conception dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Une fois que vous avez terminé les questions initiales de l’entretien, vous pouvez modifier le nom de domaine complet (FQDN) et les adresses IP pour le site. Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.

L’outil de planification affiche la topologie de site pour le site sélectionné. Le bas de la page du site comporte quatre onglets :

![Outil de planification topologie de site](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Outil de planification topologie de site")

  - Topologie du site – La page affichée avec une représentation visuelle de la topologie recommandée.

  - Diagramme de réseau Edge : la page réseau de tâches Edge est l’endroit où le concepteur effectue la plus grande partie du travail dans l’outil de planification. Le diagramme affiche la configuration réseau d’une topologie Lync Server 2013 recommandée, avec des entrées modifiables pour les adresses IP et les noms de domaine complets (FQDN) des serveurs, des pools et des équilibreurs de charge DNS (Domain Name System) et physiques.

  - Rapport de l’administrateur du périmètre – Ce rapport contient quatre rapports :
    
    ![Page rapport d’administration Edge](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Page rapport d’administration Edge")  
    
      - Rapport récapitulatif – Rapport général des paramètres de la configuration du réseau de périmètre. Si vous modifiez les valeurs de la page **réseau de tâches Edge** sur le port TCP/IP de topologie et que les valeurs de nom de domaine complet de sont utilisées dans le déploiement réel, ces adresses et noms seront représentés ici. Dans le cas contraire, le texte par défaut s’affiche.
    
      - Rapport sur les certificats – Ce rapport répertorie les noms de sujet et les noms de sujet alternatifs requis pour la topologie.
    
      - Rapport sur les pare-feu – Ce rapport répertorie les informations nécessaires pour configurer les pare-feu du périmètre dans l’infrastructure. Cela inclut les adresses IP (valeurs par défaut ou valeurs modifiées), le rôle serveur, l’adresse IP et le port source, l’adresse IP et le port de destination, le protocole de transport, le protocole d’application et les remarques pertinentes.
    
      - Rapport DNS : le rapport DNS répertorie les informations pertinentes pour les entrées DNS que vous devez créer. Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.

  - Résumé du site : le résumé du site présente une vue d’ensemble des sélections effectuées en répondant aux questions initiales de l’entretien ou en remplissant les valeurs dans les **sites de conception**. Des informations sur la capacité sont également présentées.
    
    <div>
    

    > [!NOTE]  
    > Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas apparaître pour certaines conceptions.

    
    </div>

<div>

## <a name="see-also"></a>Voir aussi


[Modification du diagramme de configuration réseau dans Lync Server 2013](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

