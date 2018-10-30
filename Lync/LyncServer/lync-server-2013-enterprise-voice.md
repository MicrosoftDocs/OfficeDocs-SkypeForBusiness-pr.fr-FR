---
title: Voix Entreprise dans Lync Server 2013
TOCTitle: Voix Entreprise
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg417163(v=OCS.15)
ms:contentKeyID: 49298820
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Voix Entreprise dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-04-08_

Avec Voix Entreprise, Lync Server inclut un protocole autonome Voix sur Internet (VoIP) qui permet d’améliorer ou de remplacer les systèmes PBX (Private Branch Exchange) traditionnels. Les utilisateurs Voix Entreprise peuvent appeler leurs collègues sur le réseau VoIP ou le PBX de votre entreprise, et passer des appels traditionnels externes. La solution Voix Entreprise intègre des fonctionnalités d’appel standard (réponse, transfert, mise en attente, redirection, parcage et libération d’appel, par exemple), et prend également en charge les appels Enhanced 9-1-1 (E9-1-1). Notez que E9-1-1 n’est disponible qu’aux États-Unis. Voix Entreprise prend également en charge une gamme étendue de périphériques IP et USB actuels et plus anciens.

## Émission et réception d’appels

En utilisant Lync, les utilisateurs peuvent passer des appels en tapant un nom ou un numéro de téléphone sur leur clavier ou en utilisant le pavé de numérotation affiché sur leur écran. Ils peuvent également passer des appels directement à partir de leur liste des contacts. Vous pouvez également déployer des périphériques Lync Phone Edition qui sont des périphériques de téléphonie IP autonomes fournis par les partenaires Microsoft.

Les utilisateurs peuvent enregistrer plusieurs périphériques de téléphonie dans Lync Server et passer facilement de l’un à l’autre.

En cas d’appel entrant, les utilisateurs sont avertis simultanément sur tous leurs périphériques par des sonneries personnalisables sur les périphériques de téléphonie IP et par une notification similaire à un message instantané sur leur PC.

Ils peuvent également définir un numéro de téléphone auquel ils peuvent être contactés sur leur téléphone de bureau, leur PC et leur téléphone mobile.

## Fonctionnalités d’appel de base

Lorsqu’il téléphone, un utilisateur peut répondre à d’autres appels entrants ou passer des appels sortants : l’appel en cours est alors automatiquement mis en attente. Il est possible de transférer un appel d’un utilisateur à l’autre, soit directement, soit après que le premier utilisateur ait parlé en privé au deuxième utilisateur. Les utilisateurs peuvent également transférer un appel vers un autre périphérique, par exemple, vers leur téléphone mobile, lorsqu’ils quittent le bureau.

## Fonctionnalités de communication plus puissantes

Lorsqu’il parle à un autre utilisateur avec Lync, un utilisateur peut facilement ajouter du texte et un contenu vidéo ou partager son Bureau pendant la conversation. La fonctionnalité Ne pas déranger est intégrée aux paramètres de présence dans Lync.

Avec messagerie unifiée Exchange, Lync et Lync Server s’intègrent à Microsoft Exchange Server 2013 et Microsoft Outlook 2013. Ainsi, les utilisateurs peuvent voir s’ils ont un nouveau message vocal dans la fenêtre Lync et dans la messagerie électronique. Si le message vocal est enregistré dans un message électronique, l’utilisateur peut cliquer dessus pour l’écouter ou afficher la transcription du message vocal.

## Fonctionnalités d’appel avancées

Voix Entreprise regroupe également plusieurs fonctionnalités d’appel avancées, telles que la délégation d’appel, les appels d’équipe, la prise d’appel de groupe et les services Response Group.

La délégation permet aux utilisateurs de déléguer la gestion des appels à un ou plusieurs assistants. Le délégué peut effectuer plusieurs tâches d’appel au nom de l’utilisateur, y compris le filtrage et l’émission d’appels ou l’initialisation de conférences.

L’appel d’équipe permet à un utilisateur de faire sonner simultanément les téléphones de ses collègues en cas d’appel entrant, ce qui permet à n’importe quel membre de l’équipe de répondre à l’appel.

La Prise d’appel de groupe, une nouvelle fonctionnalité de la Mise à jour cumulative pour Lync Server 2013de février 2013, permet aux utilisateurs de répondre, sur leur propre téléphone, à des appels entrants destinés à leurs collègues. Cette fonctionnalité diffère de l’appel d’équipe principalement dans le sens où un appel entrant sonne uniquement sur le téléphone du destinataire prévu, mais n’importe quel autre utilisateur peut choisir d’y répondre en composant un numéro de groupe de prise d’appel.

Le service Response Group peut être configuré en vue de mettre en attente et d’acheminer intelligemment les appels vers des agents désignés. Les supports techniques informatiques, les services d’assistance téléphoniques des ressources humaines et d’autres centres de contact internes l’utilisent couramment.

## Administration de Voix Entreprise

Lync Server utilise des interfaces standard et publiées pour interagir avec l’infrastructure existante. Il prend en charge les options de passerelle et SIP (comme la jonction SIP) pour permettre l’interconnexion avec les systèmes PBX IP et les réseaux RTC afin que vous puissiez migrer progressivement les utilisateurs vers Voix Entreprise, tout en minimisant les risques d’interruption. Lync Server prend en charge les codecs traditionnels, tels que G.711, G.722 et G.723.1, pour garantir l’interopérabilité avec les solutions VoIP traditionnelles.

Grâce au contrôle d’admission des appels (CAC), les administrateurs peuvent limiter le trafic audio et vidéo Lync Server acheminé sur des liaisons réseau restreintes, et spécifier ce qu’il faut faire si un nouvel appel dépasse cette limite. Par exemple, l’appel peut être routé par un autre chemin ou refusé.

Lync Server fonctionne avec des Survivable Branch Appliances tiers pour fournir des services d’appel local et une connexion RTC dans les succursales, au cas où la liaison du réseau étendu tomberait en panne sur le site central.

