---
title: 'Lync Server 2013 : Modification de la conception'
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
ms.openlocfilehash: dfce3bc4242140364005a9a981282ecb90a42d3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>Modification de la conception dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.

L’outil de planification affiche la topologie de site pour le site sélectionné. Le bas de la page du site comporte quatre onglets :

![Topologie de site outil de planification](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topologie de site outil de planification")

  - Topologie du site - La page affichée avec une représentation visuelle de la topologie recommandée.

  - Diagramme de réseau Edge : la page de diagramme de réseau Edge est l’endroit où le concepteur exécute la majeure partie du travail dans l’outil de planification. Le diagramme affiche la configuration réseau pour une topologie Lync Server 2013 recommandée, avec des entrées modifiables pour les adresses IP et les noms de domaine complets pour les serveurs, le pool, et les équilibreurs de charge du système de noms de domaine et de domaine (DNS).

  - Rapport de l’administrateur du périmètre - Ce rapport contient quatre rapports :
    
    ![Page rapport d’administration Edge](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Page rapport d’administration Edge")  
    
      - Rapport récapitulatif - Rapport général des paramètres de la configuration du réseau de périmètre. Si vous calez les valeurs de la page **Diagramme du réseau de périmètre** sur les valeurs des adresses TCP/IP et des noms de domaine complets qui seront utilisées dans la topologie du déploiement, ces adresses et noms seront représentés ici. Sinon, les valeurs par défaut s’afficheront.
    
      - Rapport sur les certificats - Ce rapport répertorie les noms de sujet et les noms de sujet alternatifs requis pour la topologie.
    
      - Rapport sur les pare-feu - Ce rapport répertorie les informations nécessaires pour configurer les pare-feu du périmètre dans l’infrastructure. Il s’agit des adresses IP (valeurs par défaut ou valeurs modifiées), des rôles serveur, des ports et adresses IP source et de destination, des protocoles de transport, des protocoles d’application et de remarques pertinentes.
    
      - Rapport DNS - Ce rapport répertorie les informations pertinentes pour les entrées DNS que vous devez créer. Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.

  - Résumé du site - Le résumé du site présente une vue d’ensemble des sélections que vous avez effectuées en répondant aux questions initiales ou en indiquant les valeurs dans **Concevoir des sites**. Les informations de capacité sont également présentées.
    
    <div>
    

    > [!NOTE]  
    > Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas s’afficher pour certaines conceptions.

    
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

