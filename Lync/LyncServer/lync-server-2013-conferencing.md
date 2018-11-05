---
title: Conférence Lync Server 2013
TOCTitle: Conférence
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg417161(v=OCS.15)
ms:contentKeyID: 49297376
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conférence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-11_

Grâce à la conférence unifiée dans Lync Server 2013, les utilisateurs peuvent collaborer, partager des informations et coordonner leurs efforts en temps réel. Tous vos utilisateurs peuvent recourir à l’ensemble des outils de réunion planifiée et de collaboration spontanée. Les fonctionnalités de conférence audio et vidéo peuvent être utilisées depuis n’importe quel emplacement offrant une connexion à Internet, et les utilisateurs n’ayant pas d’ordinateur à leur disposition peuvent participer aux conférences audio en se connectant via un téléphone RTC (réseau téléphonique commuté).

Les outils de réunion intégrés à Outlook permettent aux organisateurs de planifier une réunion ou d’initier une conférence improvisée en un seul clic, et donnent la possibilité aux participants de joindre la conférence tout aussi facilement. Un client web étend les nombreuses fonctionnalités de conférence aux participants qui exécutent la version de bureau de Lync.

## Conférence audio et vidéo

Lync Server offre une expérience utilisateur déjà connue des utilisateurs de services de pont audio classiques, notamment les services d’accès RTC avec commandes de contrôle d’appel par tonalité. Il contient en outre de puissantes fonctionnalités de planification, de participation et de gestion qui sont uniquement disponibles avec une plateforme de communications unifiées intégrée.

En un seul clic, les utilisateurs peuvent planifier une réunion à partir d’Outlook. Les informations comme l’heure de la réunion, le lieu et les participants sont basées sur le modèle Outlook classique. De plus, les informations spécifiques à la téléconférence, telles que le numéro de connexion, les ID de réunion et les rappels de code confidentiel sont automatiquement renseignées.

Pour que vous puissiez vous assurer que seules les personnes autorisées peuvent participer à un appel, Lync Server fournit plusieurs niveaux d’authentification pour les participants. Les utilisateurs qui participent via Lync sont déjà authentifiés par les services de domaine Active Directory (AD DS) et ne doivent entrer ni code confidentiel, ni code d’accès, ni ID de réunion.

Lync simplifie l’expérience utilisateur en matière de vidéoconférence, en intégrant la vidéo au client unifié afin que la planification d’une réunion avec vidéo ou l’activation spontanée de la vidéo soit simple et transparente.

Lync Server permet d’ajouter en un seul clic de la vidéo à un appel téléphonique standard. Lorsqu’une conférence ou un appel vidéo englobe plusieurs participants, chaque utilisateur peut voir simultanément les vidéos de cinq autres utilisateurs au maximum ou un présentateur peut choisir une source vidéo qui sera diffusée exclusivement à tout le monde.

La vidéo haute définition (résolution 1270 x 720 ; proportions 16:9) et la vidéo VGA (résolution 640 x 480 ; proportions 4:3) sont prises en charge pour les appels P2P entre les utilisateurs qui exécutent Lync sur des ordinateurs haut de gamme. La résolution perçue par chaque participant lors d’une même conversation peut varier en fonction des capacités vidéo de leur matériel respectif.

Les administrateurs informatiques peuvent définir des stratégies pour restreindre ou désactiver la vidéo haute définition ou VGA sur certains clients, en fonction des capacités de l’ordinateur, de la bande passante du réseau et de la présence d’une caméra capable de fournir la résolution requise. Ces stratégies sont appliquées via un provisionnement intrabande.

## Conférence Web

Lync Server intègre des fonctionnalités de partage dans les conférences grâce auxquelles vous pouvez notamment partager le Bureau, des applications, des pièces jointes, des tableaux blancs, des sondages et des documents PowerPoint dans l’interface rationalisée de Lync. En combinant cette fonctionnalité à la conférence audio ou vidéo, vous obtenez une session hautement collaborative et efficace, et très simple à administrer.

Pour améliorer l’expérience globale des utilisateurs présentant ou affichant des présentations PowerPoint, Lync Server 2013 a recours à Office Web Apps pour gérer les présentations PowerPoint. Les utilisateurs peuvent partager une photo ou copier et coller du texte à l’aide d’un tableau blanc dans la réunion Lync. Les présentateurs peuvent réaliser des sondages dans la réunion Lync pour recueillir les commentaires des participants.

Le partage du Bureau permet aux présentateurs de diffuser en temps réel des visuels, des applications, des pages web, des documents, des logiciels ou une partie de leur Bureau aux participants distants à partir de Lync. Les participants peuvent ainsi visualiser les mouvements de la souris et les éléments saisis via le clavier. Les présentateurs peuvent choisir de partager l’intégralité de l’écran ou seulement une partie de celui-ci. En partageant leur Bureau, les présentateurs peuvent proposer aux participants des démonstrations interactives sur des produits ou des logiciels, peu importe où ils se trouvent.

Le partage d’application permet aux présentateurs de partager le contrôle des logiciels sur leur Bureau sans perdre de vue les commentaires ou les questions textuelles des participants. Les présentateurs peuvent aussi déléguer le contrôle de l’application aux participants à la réunion.

## Conférence rendez-vous

Les utilisateurs ne disposant pas d’un ordinateur personnel peuvent recourir à plusieurs méthodes pour participer à une téléconférence Lync Server. Un utilisateur RTC peut composer un numéro d’accès, accéder au pont de réunion, puis entrer l’ID de réunion. Pour des réunions davantage sécurisées, le système peut aussi inviter l’utilisateur à entrer son code confidentiel afin de s’authentifier sur Active Directory. Lync Server prend également en charge les périphériques Lync Phone Edition, qui sont des périphériques téléphoniques IP autonomes fournis par des partenaires de Microsoft.

