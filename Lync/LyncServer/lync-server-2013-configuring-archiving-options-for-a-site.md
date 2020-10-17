---
title: 'Lync Server 2013 : configuration des options d’archivage pour un site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4e1a6480102c9cc4fe13e2cf651e0ab14bae7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502271"
---
# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Configuration des options d’archivage pour un site dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Vous pouvez spécifier l’application d’options d’archivage à des sites spécifiques en créant et en configurant les options appropriées dans une configuration d’archivage pour chacun de ces sites. La configuration d’un site remplace la configuration globale, mais uniquement pour le site spécifié dans la configuration du site.

Pour plus d’informations sur le fonctionnement des configurations d’archivage, notamment la hiérarchie des configurations globale, de site et de pool, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

<div>


> [!NOTE]  
> Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage.



</div>

<div>


> [!IMPORTANT]  
> Pour activer l’archivage, vous devez spécifier les stratégies d’archivage qui contrôlent l’archivage des communications internes et externes au niveau global et, si nécessaire, au niveau utilisateur et au niveau du site. Si vous configurez des stratégies de niveau utilisateur, vous devez également assigner les stratégies utilisateur à des utilisateurs spécifiques. Pour plus d’informations sur la création et la configuration de stratégies d’archivage, voir <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and External Communications in Lync Server 2013</A> dans la documentation des opérations.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>Pour configurer les options d’archivage au niveau du site

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.

4.  Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du site**.

5.  Dans **Sélectionner un site**, choisissez le site à configurer pour l’archivage.

6.  Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
      - Afin d’activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
      - Afin d’activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée / conférence Web**.
    
      - Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.

7.  Dans **Créer un paramètre d’archivage**, procédez comme suit :
    
      - Pour bloquer toute activité quand l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
      - Pour utiliser Microsoft Exchange Server afin de stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .
    
      - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
        
          - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.
        
          - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.

8.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

