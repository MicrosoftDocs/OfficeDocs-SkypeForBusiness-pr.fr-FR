---
title: Test de l’évolutivité
TOCTitle: Test de l’évolutivité
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205226(v=OCS.15)
ms:contentKeyID: 49298693
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test de l’évolutivité

 

_**Dernière rubrique modifiée :** 2012-10-01_

Lync Server 2013 fournit l’infrastructure serveur pour toutes les communications Lync Server en temps réel, y compris les messages instantanés et la présence, les conférences et les Voix Entreprise. Cela inclut toutes les fonctionnalités qui consomment des ressources matérielles d’un pool Lync Server 2013 et qui, par conséquent, peuvent avoir un impact sur les performances et la mise à l’échelle. Selon les organisations, les fonctionnalités ne sont pas toutes utilisées de la même façon.

À titre d’exemple, certaines organisations ont très souvent recours à la vidéo lors des conférences alors que d’autres l’utilisent peu ou pas du tout. De la même façon, certaines organisations préfèrent le partage de présentations PowerPoint au partage d’application (ou inversement). Les organisations qui déploient la fonctionnalité Voix Entreprise peuvent choisir d’utiliser massivement ou non l’application Response Group. La plupart des organisations déploient des serveurs de surveillance, mais peu d’entre elles déploient des serveurs d’archivage. Par ailleurs, toutes les organisations ne disposent pas d’infrastructures identiques, tant sur le plan des capacités matérielles ou réseau que du nombre et de la taille des pools déployés. La diversité des fonctionnalités et infrastructures déployées complique les tests d’extensibilité, car il est impossible de simuler toutes les combinaisons possibles de fonctionnalités et d’infrastructures.

Pour déterminer le niveau d’extensibilité pour Lync Server, nous effectuons des tests en utilisant toutes les fonctionnalités de Lync Server en même temps, d’après un modèle d’utilisation courant (modèle utilisateur). Pour trouver un modèle utilisateur approprié pour les charges de travail Lync Server, nous analysons un grand nombre de données, telles que les résultats des enquêtes utilisateur, les commentaires renvoyés dans le cadre du Programme d’amélioration de l’expérience utilisateur Microsoft, les données sur l’utilisation de Lync Server fournies par le service informatique interne de Microsoft ainsi que les données d’analyse de notre service Live Meeting. Dans de nombreux cas, le modèle utilisateur prévoit des charges de travail plus lourdes afin de laisser une marge de manœuvre confortable pour l’organisation.

Pour réaliser nos tests d’extensibilité, nous installons et configurons des pools Lync Server 2013 conformes aux configurations matérielle et logicielle recommandées, notamment en ce qui concerne les composants d’infrastructure, tels que les services de domaine Active Directory, les programmes d’équilibrage de la charge matérielle et les pare-feu. Nous déployons des environnements Lync Server qui se rapprochent le plus possible d’environnements standard réels. Ensuite, avec l’outil de test de contrainte et de performances de Lync Server 2013, nous simulons les charges de travail Lync Server 2013 sur la base du modèle utilisateur que nous avons défini.

Nous effectuons plusieurs phases de tests d’extensibilité (sur plusieurs cycles de test de trois semaines chacun). Nous nous appuyons sur les résultats de l’ensemble des tests pour mieux régler les performances et vérifier la prise en charge des valeurs d’extensibilité dans notre modèle utilisateur.

