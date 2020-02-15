---
title: 'Lync Server 2013 : outils d’administration Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6de54e91129351a153c9cf4e08925d62eeb342c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Outils d’administration Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Cette rubrique décrit les outils d’administration de Lync Server 2013.

Les outils d’administration sont installés par défaut sur chaque serveur Lync Server. Vous pouvez également les installer sur d’autres ordinateurs, notamment des consoles d’administration dédiées. Pour connaître les procédures d’installation des outils d’administration, reportez-vous à la rubrique [install Lync Server 2013 administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md). Pour connaître les procédures permettant d’ouvrir les outils permettant d’effectuer des tâches de gestion, reportez-vous à la rubrique [Open Lync Server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

Avant d’installer ou d’utiliser les outils d’administration Lync Server, vérifiez que vous avez examiné les exigences en matière d’infrastructure, de système d’exploitation, de logiciel et d’administrateur. Pour plus d’informations sur les exigences d’infrastructure, voir [administrative Tools infrastructure Requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Pour plus d’informations sur le système d’exploitation et la configuration logicielle requise pour l’installation des outils d’administration de Lync Server, voir [serveur et outils pris en charge par le système d’exploitation dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [autres logiciels requis pour Lync Server 2013](lync-server-2013-additional-software-requirements.md), ainsi que la [prise en charge et les exigences des serveurs supplémentaires dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Les droits et autorisations de l’utilisateur nécessaires à l’installation et à l’utilisation des outils sont décrits dans la section [droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

Les outils d’administration se composent des éléments suivants :

  - **L’Assistant**   déploiement Lync Server permet de déployer Lync Server et d’installer tous les outils d’administration.

  - **Le générateur**   de topologies Lync Server permet de définir les composants de votre déploiement.

  - **Le panneau de configuration**   Lync Server permet de gérer en continu votre déploiement à l’aide d’une interface Web.

  - **Lync Server Management Shell**   utilisez pour la gestion continue de votre déploiement à l’aide de la ligne de commande.

  - **Outil de journalisation Lync Server**   utilisé pour résoudre les problèmes de votre déploiement.

  - **Le service**   de journalisation centralisée collecte les fichiers journaux et de suivi à partir d’un ordinateur, d’un pool, d’un site ou d’un global. Sélectionnez et définissez des scénarios qui contiennent des fournisseurs, des indicateurs et des niveaux de suivi. La journalisation est collectée, agrégée et affichée avec des outils tels que n’importe quel outil basé sur du texte ou Snooper. exe.

Vous pouvez gérer votre déploiement en utilisant principalement le générateur de topologie et le panneau de configuration Lync Server.

<div>

## <a name="deployment-wizard"></a>Assistant Déploiement

Vous devez utiliser l’Assistant Déploiement Lync Server inclus sur le support d’installation pour installer tous les outils d’administration sur un ordinateur sur lequel vous n’avez pas encore installé Lync Server. Pendant le processus d’installation des outils d’administration, l’Assistant Déploiement de Lync Server est installé localement avec les autres outils de sorte que vous puissiez l’utiliser ultérieurement pour installer des fichiers pour des composants supplémentaires ou supprimer des fichiers pour les composants dont vous ne voulez pas sur le ci.

Pour plus d’informations sur l’exécution de l’Assistant Déploiement de Lync Server pour la première fois à partir du support d’installation de Lync Server, voir [install Lync server 2013 administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

</div>

<div>

## <a name="topology-builder"></a>Générateur de topologies

Pour plus d’informations sur les tâches de déploiement que vous pouvez effectuer à l’aide du générateur de topologie, reportez-vous à la documentation de déploiement pour chaque rôle serveur.

</div>

<div>

## <a name="lync-server-control-panel"></a>Panneau de commande Lync Server

Vous pouvez utiliser le panneau de configuration Lync Server 2013 pour effectuer la plupart des tâches d’administration nécessaires à la gestion et à la maintenance de Lync Server 2013. Le panneau de configuration Lync Server vous fournit une interface utilisateur graphique (GUI) pour gérer la configuration des serveurs exécutant Lync Server, en plus des utilisateurs, des clients et des appareils de votre organisation. Lync Server Management Shell utilise le panneau de configuration Lync Server comme mécanisme sous-jacent pour effectuer la configuration de Lync Server.

Le panneau de configuration Lync Server est automatiquement installé sur chaque serveur frontal Lync Server ou serveur Standard Edition. Dans cette version, l’administration des serveurs Edge s’effectue à distance. Vous pouvez également installer le panneau de configuration Lync Server sur un autre ordinateur, tel qu’une console de gestion à partir de laquelle vous souhaitez centraliser la gestion de Lync Server. Pour plus d’informations, reportez-vous à la rubrique [install Lync Server 2013 administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Pour configurer les paramètres à l’aide du panneau de configuration Lync Server, vous devez être connecté à l’aide d’un compte affecté au rôle CsAdministrator. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Lync Server 2013, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync server 2013</A>.</P>
> <LI>
> <P>Pour configurer les paramètres à l’aide du panneau de configuration Lync Server, vous devez également utiliser un ordinateur avec une résolution d’écran minimale de 1024 x 768.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server Management Shell

Dans Lync Server, Lync Server Management Shell fournit une nouvelle méthode d’administration et de gestion. Lync Server Management Shell est une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell, qui inclut un ensemble complet d’applets de commande propres à Lync Server. Avec Lync Server Management Shell, vous bénéficiez d’un ensemble complet de contrôles de configuration et d’automatisation. Le générateur de topologie et le panneau de configuration Lync Server implémentent tous deux des sous-ensembles de ces applets de commande pour prendre en charge la gestion de Lync Server. Lync Server Management Shell inclut des applets de commande pour toutes les tâches d’administration de Lync Server, et vous pouvez utiliser les applets de commande individuellement pour gérer votre déploiement. Pour plus d’informations, reportez-vous à la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) ou à l’aide de ligne de commande pour chaque cmdlet.

</div>

<div>

## <a name="logging-tool"></a>Outil de journalisation

L’outil de journalisation Lync Server facilite la résolution des problèmes en capturant les informations de journalisation et de suivi du produit pendant que le produit est en cours d’exécution. Vous pouvez utiliser l’outil pour exécuter des sessions de débogage sur n’importe quel rôle de serveur Lync Server. Pour plus d’informations sur l’outil de journalisation, voir la documentation de l’outil de journalisation [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Lync Server 2010 dans la bibliothèque TechNet à l’adresse.

<div>


> [!IMPORTANT]  
> Le service de journalisation centralisée est recommandé pour toutes les collections de journalisation sur l’outil de journalisation Lync Server dans toutes les circonstances. L’outil de journalisation Lync Server continue de fonctionner, mais il interfère ou s’affiche principalement si le service de journalisation centralisée est déjà en cours d’exécution. Vous devez utiliser uniquement le service de journalisation centralisée ou l’outil de journalisation Lync Server, mais jamais les deux à la fois. Pour plus d’informations sur le service de journalisation centralisée et la raison pour laquelle vous devez l’utiliser exclusivement, voir <A href="lync-server-2013-using-the-centralized-logging-service.md">utilisation du service de journalisation centralisée dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration requise pour l’infrastructure des outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Configuration logicielle requise pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Conditions requises pour publier une topologie dans Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Installer les outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Ouvrir les outils d’administration de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Dépannage du panneau de configuration Lync Server 2013](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Utilisation du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

