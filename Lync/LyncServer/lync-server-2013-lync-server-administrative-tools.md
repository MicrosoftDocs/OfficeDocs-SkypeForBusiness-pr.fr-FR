---
title: 'Lync Server 2013 : Outils d’administration de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6756aee8d7c65b179fb5c1c15ca008b3bd205778
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Outils d’administration de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Cette rubrique décrit les outils d’administration de Lync Server 2013.

Les outils d’administration sont installés par défaut sur chaque serveur Lync Server. Par ailleurs, vous pouvez installer les outils d’administration sur d’autres ordinateurs, par exemple des consoles d’administration dédiées. Pour connaître les procédures d’installation des outils d’administration, voir [installer les outils d’administration de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md). Pour consulter les procédures permettant d’ouvrir les outils d’exécution des tâches de gestion, voir [ouvrir les outils d’administration de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

Vérifiez que vous passez en revue les exigences en matière d’infrastructure, de système d’exploitation, de logiciels et de droits d’administrateur avant d’installer ou d’utiliser les outils d’administration de Lync Server. Pour plus d’informations sur la configuration requise en matière d’infrastructure, voir la [Configuration requise infrastructure des outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Pour plus d’informations sur le système d’exploitation et la configuration logicielle requise pour l’installation des outils d’administration de Lync Server, reportez-vous à la rubrique [prise en charge des systèmes d’exploitation serveur et outils dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md)et [ La prise en charge et les exigences serveur supplémentaires dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Les droits d’utilisateur et les autorisations nécessaires pour installer et utiliser les outils sont décrits dans [droits d’administrateur et autorisations nécessaires pour l’installation et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

Les outils d’administration sont les suivants:

  - **L’Assistant**   déploiement de Lync Server vous permet de déployer Lync Server et d’installer tous les outils d’administration.

  - **Le générateur**   de topologie Lync Server permet de définir des composants dans votre déploiement.

  - **Panneau de configuration**   de Lync Server pour une gestion suivie de votre déploiement à l’aide d’une interface basée sur le Web.

  - **Lync Server Management Shell**   vous permet d’utiliser la ligne de commande pour gérer en continu votre déploiement.

  - **Outil de journalisation Lync Server**   à utiliser pour résoudre les problèmes de votre déploiement.

  - **Le service**   de connexion centralisé collecte les journaux et trace les fichiers à partir d’un ordinateur, d’une réserve, d’un site ou d’une connexion globale. Sélectionner et définir des scénarios qui contiennent des fournisseurs, des indicateurs et des niveaux de suivi. La journalisation est collectée, agrégée et affichée à l’aide d’outils tels que des outils de texte ou de la fonction Snoop. exe.

Vous pouvez gérer votre déploiement en utilisant essentiellement le générateur de topologie et le panneau de configuration de Lync Server.

<div>

## <a name="deployment-wizard"></a>Assistant Déploiement

Vous devez utiliser l’Assistant Déploiement de Lync Server inclus sur le média d’installation pour installer tous les outils d’administration sur un ordinateur sur lequel vous n’avez pas encore installé Lync Server. Pendant le processus d’installation des outils d’administration, l’Assistant Déploiement de Lync Server est installé en local avec les autres outils de sorte que vous puissiez l’utiliser ultérieurement pour installer des fichiers pour les composants supplémentaires ou supprimer des fichiers pour les composants que vous ne souhaitez pas voir sur le ordinateur.

Pour plus d’informations sur l’exécution de l’Assistant Déploiement de Lync Server pour la première fois à partir du support d’installation de Lync Server, voir [installer les outils d’administration de Lync server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

</div>

<div>

## <a name="topology-builder"></a>Générateur de topologie

Pour plus d’informations sur les tâches de déploiement que vous pouvez effectuer à l’aide du générateur de topologie, consultez la documentation de déploiement pour chaque rôle de serveur.

</div>

<div>

## <a name="lync-server-control-panel"></a>Panneau de configuration Lync Server

Vous pouvez utiliser le panneau de configuration de Lync Server 2013 pour effectuer la plupart des tâches administratives nécessaires à la gestion et à la gestion de Lync Server 2013. Le panneau de configuration de Lync Server vous offre une interface utilisateur graphique (GUI) pour gérer la configuration des serveurs exécutant Lync Server, en plus des utilisateurs, des clients et des appareils de votre organisation. Lync Server Management Shell utilise le panneau de configuration de Lync Server comme mécanisme sous-jacent pour effectuer la configuration de Lync Server.

Le panneau de configuration de Lync Server est automatiquement installé sur tous les serveurs front end Server Lync Server ou Standard Edition Server. Dans cette version, vous administrez les serveurs Edge à distance. Vous pouvez également installer le panneau de configuration de Lync Server sur un autre ordinateur, tel qu’une console de gestion à partir de laquelle vous voulez gérer de manière centralisée Lync Server. Pour en savoir plus, voir [installer les outils d’administration de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Pour configurer les paramètres à l’aide du panneau de configuration de Lync Server, vous devez être connecté à l’aide d’un compte attribué au rôle CsAdministrator. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Lync Server 2013, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planification du contrôle d’accès basé sur les rôles dans Lync server 2013</A>.</P>
> <LI>
> <P>Pour configurer les paramètres à l’aide du panneau de configuration de Lync Server, vous devez également utiliser un ordinateur avec une résolution d’écran minimum de 1024 x 768.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server Management Shell

Dans Lync Server, Lync Server Management Shell fournit une nouvelle méthode d’administration et de gestion. Lync Server Management Shell est une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell, qui inclut un ensemble complet d’applets de commande spécifiques à Lync Server. Lync Server Management Shell vous permet d’accéder à un large éventail de contrôles de configuration et d’automatisation. Le générateur de topologie et le panneau de configuration de Lync Server implémentent les sous-ensembles de ces applets de commande pour la prise en charge de la gestion de Lync Server. Lync Server Management Shell inclut des cmdlets pour toutes les tâches d’administration de Lync Server et vous pouvez utiliser les applets de cmdlet individuellement pour gérer votre déploiement. Pour plus d’informations, reportez-vous à la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) ou à l’aide de la ligne de commande pour chaque cmdlet.

</div>

<div>

## <a name="logging-tool"></a>Outil d’enregistrement

L’outil de journalisation de Lync Server facilite la résolution des problèmes en capturant les informations de journalisation et de suivi à partir du produit lorsque le produit est en cours d’exécution. Vous pouvez utiliser l’outil pour exécuter des sessions de débogage sur n’importe quel rôle serveur Lync Server. Pour plus d’informations sur l’outil de journalisation, voir la documentation de l’outil de journalisation [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Lync Server 2010 dans la bibliothèque TechNet à l’adresse.

<div>


> [!IMPORTANT]  
> Le service de journalisation centralisé est recommandé pour toutes les collections de journaux par le biais de l’outil de journalisation Lync Server en toutes circonstances. L’outil de journalisation de Lync Server fonctionne toujours, mais il interfère ou s’affiche de façon plus efficace si le service de journalisation centralisé est déjà en cours d’exécution. Vous devez uniquement utiliser le service de journalisation centralisé ou l’outil de journalisation de Lync Server, mais jamais les deux simultanément. Pour plus d’informations sur le service de journalisation centralisé et sur les raisons pour lesquelles vous devriez l’utiliser exclusivement, voir <A href="lync-server-2013-using-the-centralized-logging-service.md">utiliser le service de journalisation centralisé dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Exigences d’infrastructure des outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Configuration logicielle requise pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Conditions requises pour publier une topologie dans Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Ouvrez les outils d’administration de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Résolution des problèmes liés à Lync Server 2013 Control Panel](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Utiliser le service de journalisation centralisé dans Lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

