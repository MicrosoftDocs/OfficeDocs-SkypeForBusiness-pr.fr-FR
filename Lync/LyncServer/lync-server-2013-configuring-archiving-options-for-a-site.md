---
title: 'Lync Server 2013 : configuration des options d’archivage d’un site'
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
ms.openlocfilehash: cb2b70242388ca00a7bf43ec535ae1231fb77644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Configuration des options d’archivage d’un site dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Vous pouvez spécifier des options d’archivage qui doivent être appliquées à des sites spécifiques en créant et en configurant des options dans une configuration de l’archivage pour chacun de ces sites. Une configuration de site ne remplace la configuration globale que pour le site spécifié dans la configuration du site. Les configurations de pool remplacent les configurations de site.

Pour plus d’informations sur le fonctionnement des configurations d’archivage, y compris la hiérarchie des configurations globales, de site et de pool, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

<div>


> [!NOTE]  
> Vous devez spécifier toutes les options appropriées dans les configurations d’archivage avant de procéder à l’archivage.



</div>

<div>


> [!IMPORTANT]  
> Pour activer l’archivage, vous devez spécifier les stratégies d’archivage qui contrôlent l’archivage des communications internes et externes au niveau global et, si nécessaire, au niveau utilisateur et au niveau du site. Si vous configurez des stratégies de niveau utilisateur, vous devez également assigner les stratégies utilisateur à des utilisateurs spécifiques. Pour plus d’informations sur la création et la configuration de stratégies d’archivage, voir <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">gestion de l’archivage des communications internes et externes dans Lync Server 2013</A> dans la documentation des opérations.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>Pour configurer les options d’archivage au niveau du site

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server 2013. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server 2013, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.

4.  Sur la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du site**.

5.  Dans **Sélectionner un site**, choisissez le site à configurer pour l’archivage.

6.  Dans **Nouveau paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
      - Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
      - Afin d’activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence Web**.
    
      - Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.

7.  Par ailleurs, dans **Créer un paramètre d’archivage**, procédez comme suit :
    
      - Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.
    
      - Pour utiliser Microsoft Exchange Server pour stocker des données d’archivage, activez la case à cocher **intégration Microsoft Exchange** .
    
      - Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
        
          - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
        
          - Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.

8.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

