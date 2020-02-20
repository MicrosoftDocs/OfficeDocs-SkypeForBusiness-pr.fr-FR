---
title: 'Lync Server 2013 : configuration des options d’archivage au niveau global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 965d82f63b776ed9bc1790715b14524dd39ba054
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>Configuration des options d’archivage au niveau global dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Lorsque vous ajoutez l’archivage à votre topologie et que vous publiez la topologie, Lync Server crée une configuration globale pour l’archivage. Par défaut, aucune option d’archivage n’est activée dans la configuration globale. La configuration globale contrôle les options qui sont activées pour l’ensemble de votre déploiement, sauf si vous configurez des configurations de site ou de pool, ce qui remplace la configuration globale.

Pour plus d’informations sur le fonctionnement des configurations d’archivage, notamment la hiérarchie des configurations globale, de site et de pool, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

<div>


> [!NOTE]  
> Vous devez spécifier toutes les options appropriées pour les configurations d’archivage avant d’activer la fonctionnalité d’archivage.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>Pour configurer les options d’archivage au niveau global

1.  À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, reportez-vous à la rubrique [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.

4.  Dans la page **Configuration de l’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier le paramètre d’archivage - Global**, dans la zone de liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options suivantes :
    
      - **Désactiver l’archivage**
    
      - **Archiver les sessions de messagerie instantanée**
    
      - **Archiver les sessions de messagerie instantanée et de conférence web**

6.  Dans la page **Modifier le paramètre d’archivage - Global**, effectuez également les opérations suivantes :
    
      - Pour bloquer toute activité lorsque l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
      - Pour utiliser Microsoft Exchange Server afin de stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .
    
      - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
        
          - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.
        
          - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.

7.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

