---
title: Prise en charge des grandes réunions à l’aide de Lync Server 2013
TOCTitle: Prise en charge des grandes réunions à l’aide de Lync Server 2013
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204894(v=OCS.15)
ms:contentKeyID: 49297192
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge des grandes réunions à l’aide de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-03_

Les réunions de grande taille ne suivent pas le modèle de test décrit dans la section précédente, car elles ont les caractéristiques suivantes :

  - Le format de la réunion est celui d’une présentation un-à-plusieurs.

  - Un ou plusieurs utilisateurs constituent les présentateurs. Le reste de l’assistance constitue les participants.

  - Le partage de présentation PowerPoint est la principale activité de collaboration pour les données.

  - L’audio est nécessaire et la vidéo peut également être utilisée.

  - Une personne dédiée, généralement l’organisateur de la réunion ou un assistant de l’organisateur, prépare la réunion à l’avance.

  - Le personnel dédié (et non les présentateurs) est chargé de mener la réunion, notamment en ce qui concerne la connexion à une réunion en ligne, la vérification du bon fonctionnement de l’audio, de la vidéo et du partage des diapositives, la gestion de la salle d’attente et des rôles utilisateurs, l’activation ou la désactivation du son des participants, la gestion des questions, ainsi que la gestion des enregistrements, le cas échéant.

La prise en charge de réunions de grande taille incluant jusqu’à 1 000 utilisateurs nécessite de régler les aspects liés au modèle matériel partagé et au modèle d’absence de réservation.

Pour disposer de suffisamment de ressources aux niveaux de l’UC et de la mémoire pour les réunions incluant jusqu’à 1 000 utilisateurs, les serveurs frontaux d’hébergement ne doivent pas gérer de fonctionnalités de messagerie instantanée et de présence, ni de charges de travail liées à Voix Entreprise. Ils ne doivent pas non plus héberger d’autres réunions, quelles que soient leurs tailles. Cela signifie que l’hébergement de réunions allant jusqu’à 1 000 utilisateurs nécessite la mise en place d’un pool Lync Server distinct dédié à l’hébergement de réunions de grande taille (allant jusqu’à 1 000 utilisateurs).

Un pool Lync Server dédié à l’hébergement de réunions de grande taille ne doit accueillir qu’une seule réunion allant jusqu’à 1 000 utilisateurs. Ainsi, les heures de réunion doivent être réservées à l’avance via un processus de planification hors bande afin d’assurer une prise en charge spécifique des serveurs frontaux. Pour assurer la prise en charge de plusieurs réunions de grande taille simultanées, nous vous recommandons de configurer plusieurs pools dédiés aux réunions de grande taille.

Nous vous recommandons de dédier une personne à la conduite et au contrôle de la partie en ligne d’une réunion de grande taille. Cette personne peut être l’organisateur, un assistant de l’organisateur ou du présentateur, ou bien un membre de l’équipe de support technique dédiée aux réunions de grande taille, en fonction des préférences de l’organisation.

Dans les sections suivantes, nous décrivons l’implémentation d’un pool dédié aux réunions de grande taille, ainsi que les meilleures pratiques relatives à l’utilisation de Lync Server 2013 pour la prise en charge des scénarios impliquant des réunions de grande taille.

## Dans cette section

  - [Configuration de la prise en charge pour les grandes réunions](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Gestion des grandes réunions](lync-server-2013-managing-large-meetings.md)

