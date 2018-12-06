---
title: 'Lync Server 2013 : Emplacement de l’utilisateur'
TOCTitle: Emplacement de l’utilisateur
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994073(v=OCS.15)
ms:contentKeyID: 53095528
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Emplacement de l’utilisateur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-09_

Le routage géodépendant utilise les mêmes régions réseau, sites réseau et sous-réseaux définis dans Lync Server et utilisés pour les appels d’urgence, le contrôle d’admission des appels et la déviation du trafic multimédia pour appliquer les restrictions de routage des appels et empêcher le contournement des frais de réseau téléphonique commuté. L’emplacement d’un utilisateur est déterminé par le sous-réseau IP du ou des points de terminaison Lync depuis lesquels il est connecté. Chaque sous-réseau IP est associé à un site réseau, regroupé au sein de régions réseau définies par l’administrateur. Le routage géodépendant est appliqué sur la base du site réseau de l’utilisateur.

Les règles de routage géodépendant sont appliquées sur la base d’un site réseau. Un ensemble donné de règles est donc appliqué à tous les points de terminaison pour lesquels le routage géodépendant est activé, situés dans un même site réseau. Les administrateurs peuvent appliquer le routage géodépendant aux sites réseau qui en ont besoin.

Les stratégies de routage des communications vocales peuvent être définies sur la base des sites réseau individuels afin de définir une passerelle RTC particulière que tous les utilisateurs situés dans le site réseau doivent utiliser pour appeler les numéros de téléphone RTC. Ce type de stratégie supplante le routage défini par la stratégie de voix de l’utilisateur lorsque celui-ci est situé dans un site réseau pour lequel le routage géodépendant est activé, et empêche le routage des appels via les autres passerelles RTC pour lesquelles le routage géodépendant est activé. Lorsqu’un utilisateur Lync passe un appel RTC, sa stratégie de voix détermine s’il est autorisé à passer l’appel. Si c’est le cas, le routage géodépendant détermine la passerelle RTC depuis laquelle l’appel doit sortir en fonction de l’emplacement de l’utilisateur.

L’emplacement d’un utilisateur peut être classé comme suit :

  - L’utilisateur est situé dans un site réseau connu pour le routage géodépendant et son numéro SDA (sélection directe à l’arrivée) s’arrête sur une passerelle RTC placée dans le même site réseau (bureau). Le routage des appels sortants est effectué via la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.

  - L’utilisateur est situé dans un site réseau connu différent du site réseau dans lequel la passerelle RTC est située (l’utilisateur a été déplacé vers une autre agence). Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans d’autres sites que la passerelle RTC pour empêcher le contournement des frais de réseau téléphonique commuté.

  - Si un utilisateur est situé dans un site réseau inconnu du déploiement Lync Server, le routage des appels entrants est basé sur la stratégie de voix affectée à l’utilisateur et utilise des passerelles RTC non liées aux restrictions de routage géodépendant. Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement des frais de réseau téléphonique commuté.

## Voir aussi

#### Autres ressources

[Instructions de routage géodépendant dans Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)

