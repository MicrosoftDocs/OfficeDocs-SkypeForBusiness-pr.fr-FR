---
title: 'Lync Server 2013 : Début du processus de planification'
TOCTitle: Début du processus de planification
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398986(v=OCS.15)
ms:contentKeyID: 49299091
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Début du processus de planification pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La planification d’un déploiement de communications unifiées local pouvant sembler complexe, Lync Server vous offre deux outils très utiles :

  - **L’outil de planification** est un assistant proposant une série de questions sur votre organisation, les fonctionnalités de Lync Server à activer et les besoins nécessaires à la planification de votre capacité. Il crée ensuite une topologie de déploiement recommandée en fonction de vos réponses et génère un diagramme Microsoft Visio de ce déploiement.

  - **Générateur de topologie** est un composant d’installation de Lync Server. Vous utilisez Générateur de topologie pour créer, modifier et publier votre topologie planifiée. Il valide également votre topologie avant que vous ne commenciez à installer les serveurs. Lorsque vous installez Lync Server sur chaque serveur, il lit la topologie publiée dans le cadre du processus d’installation et le programme d’installation déploie le serveur comme indiqué dans la topologie.

## Outil de planification Lync Server

L’outil de planification sélectionne vos réponses aux questions dans l’outil et génère une topologie selon les directives et les pratiques recommandées par Lync Server. Il propose également plusieurs vues de déploiement en fonction de vos réponses. Il offre à la fois une vue globale de tous vos sites (dont les sites centraux et les sites de succursale) ainsi que des vues détaillées montrant les serveurs et autres composants de chaque site.

L’exécution de l’outil de planification ne vous limite pas à un déploiement spécifique et ne lance aucun processus. En fait, l’exécution de l’outil de planification avant même de disposer d’un plan précis peut se révéler très utile pour anticiper les questions auxquelles vous devrez répondre durant votre processus de planification.

Vous pouvez exécuter plusieurs fois l’outil de planification en répondant différemment aux questions pour comparer les résultats obtenus. Si vous êtes satisfait de votre conception mais devez la modifier, vous pouvez revenir dans l’outil de planification pour charger la conception et y apporter vos changements. L’exécution de l’outil de planification dure environ 15 minutes.

Une fois satisfait, vous pouvez utiliser l’outil de planification pour créer un diagramme de votre déploiement planifié. Vous pouvez utiliser ce diagramme lors de la création du déploiement dans le Générateur de topologie.

> [!NOTE]  
> L’outil de planification fourni avec cette version de Lync Server 2013 est une version préliminaire. Notez que les chiffres de planification de la capacité de l’outil de planification sont préliminaires, et ne sont pas pris en charge par la version finale.

## Générateur de topologie Lync Server

Une fois que vous avez déterminé votre plan de déploiement, vous utilisez le Générateur de topologie pour commencer le déploiement. Une fois terminé, vous utilisez le Générateur de topologie pour valider la topologie, puis, si tout se déroule correctement, vous pouvez publier la topologie. Lorsque vous publiez la topologie, Lync Server place celle-ci dans le magasin central de gestion créé à cet instant (si ce n’est pas déjà fait). Lorsque vous installez Lync Server sur chaque serveur de votre déploiement, le serveur lit la topologie à partir du magasin central de gestion et s’installe pour tenir son rôle dans votre déploiement.

Si vous maîtrisez parfaitement Lync Server et n’avez pas besoin d’autant de conseils, vous pouvez ignorer l’outil de planification et utiliser les assistants du Générateur de topologie pour la conception initiale de votre déploiement et pour les étapes de validation et de publication.

L’utilisation du Générateur de topologie pour planifier et publier une topologie est une étape nécessaire. Vous ne pouvez pas ignorer le Générateur de topologie et installer individuellement Lync Server sur les serveurs dans votre déploiement. Chaque serveur doit lire la topologie à partir d’une topologie validée et publiée dans le magasin central de gestion.

## Processus de planification de haut niveau

Nous vous recommandons de suivre le processus général consistant à utiliser la documentation et l’outil de planification pour planifier votre déploiement Lync Server.

1.  Si vous êtes familiarisé avec les versions précédentes de Lync Server, lisez la section [Nouvelles fonctionnalités de Lync Server 2013](lync-server-2013-new-features.md) pour vous familiariser avec les nouvelles fonctionnalités et exigences de Lync Server 2013.

2.  Consultez les autres rubriques de cette section de la documentation : [Tâches de topologie de base à connaître avant la planification pour Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md), [Décisions de planification initiale pour Lync Server 2013](lync-server-2013-initial-planning-decisions.md) et [Clients pour Lync Server 2013](lync-server-2013-clients.md). Notez les décisions de planification représentées dans [Topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Maintenez que vous êtes familiarisé avec les fonctionnalités de Lync Server et les types de questions auxquels vous devrez répondre, réexécutez l’outil de planification pour afficher en détail la topologie obtenue. Assurez-vous que la topologie s’adapte aux exigences uniques de votre entreprise.

4.  Pour plus d’informations sur des charges de travail ou des fonctionnalités particulières, lisez les sections correspondantes de la section [Planification pour Lync Server 2013](lync-server-2013-planning.md).

5.  Réexécutez l’outil de planification. Vous pouvez commencer par le déploiement que vous avez créé à l’étape 3 puis modifier les résultats, ou reprendre tout à zéro.
    
    Si nécessaire, exécutez une troisième fois l’outil de planification et répétez le processus jusqu’à obtenir le résultat souhaité.

6.  Lorsque vous avez finalisé le plan de topologie, utilisez l’outil de planification pour créer et imprimer un diagramme Visio de votre topologie. Vous pouvez utiliser cette impression durant l’utilisation du Générateur de topologie pour configurer votre topologie.

7.  Avant de lancer le déploiement, lisez les sections [Détermination de la configuration système requise pour Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) et [Définition de la configuration requise pour l’infrastructure pour Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) afin de vous familiariser avec les conditions requises et l’infrastructure nécessaire à Lync Server. Veillez également à lire toutes les sections de la rubrique [Planification pour Lync Server 2013](lync-server-2013-planning.md) relatives aux charges de travail et fonctionnalités que vous souhaitez déployer.

## Migration à partir de versions précédentes

Si vous migrez vers Lync Server à partir d’une version précédente, consultez la documentation de [Migration](migration.md) pour obtenir des instructions spécifiques à votre migration et à votre déploiement.

