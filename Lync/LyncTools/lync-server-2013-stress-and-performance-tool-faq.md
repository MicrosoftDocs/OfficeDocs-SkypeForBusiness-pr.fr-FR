---
title: Forum aux questions sur l’outil contraintes et performances de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Forum aux questions sur l’outil contraintes et performances de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Forum aux questions

Voici quelques questions fréquemment posées sur l’outil de stress et de performances de Lync Server 2013.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>Est-il possible d’exécuter LyncPerfTool. exe en production?

Nous déconseillons de le faire. Cet outil aura un impact sur les performances, la sécurité et l’interface utilisateur du serveur.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>Je me connecte pour la première fois. Pourquoi les serveurs s’exécutent-ils sur une telle charge?

La première fois que les utilisateurs se connectent, il existe d’autres opérations. C’est la raison pour laquelle les performances du serveur principal Microsoft SQL Server sont détériorées. Nous vous recommandons d’effectuer un test de courte durée de connexion pour tous les utilisateurs, puis de redémarrer les clients avant de procéder à la mesure des résultats. Nous ne prenons pas en charge plus de 12 sessions d’ouverture de session simultanées par seconde, mais cela dépend de votre configuration matérielle.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Mes clients manquent de mémoire. Que dois-je faire?

Si vos clients manquent de mémoire, vous devez réduire le nombre d’utilisateurs par ordinateur.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>Mes clients utilisent tout le temps de 100%. Que dois-je faire?

Si vos clients s’exécutent avec une UC très élevée alors que tous les utilisateurs sont connectés, vous devez réduire le nombre d’utilisateurs par ordinateur. Les pics d’UC élevés sont acceptables, mais si la charge est soutenue, vous devez réduire la charge.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>Est-il possible d’exécuter l’outil sur le serveur lui-même?

Non. Ce scénario n’est pas pris en charge et peut échouer en raison d’une incompatibilité binaire. Par ailleurs, dans la mesure où le point est de mesurer la consommation de ressources sur le serveur, l’exécution de l’outil génère un rendu inutile des mesures.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Est-il possible d’exécuter LyncPerfTool. exe sur un serveur virtuel ou sur Microsoft Hyper-V Server 2008/2012?

Oui.

</div>

<div>

## <a name="what-does-mpop-mean"></a>Qu’est-ce que MPOP?

MPOP représente plusieurs points de présence. Il est conçu pour simuler le scénario dans lequel les utilisateurs sont connectés à Lync 2013 à partir de plusieurs ordinateurs. Notez que dans LyncPerfTool. exe, chaque point de terminaison utilise le profil par défaut (autrement dit, le profil n’est pas fractionné entre les deux points de présence).

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>J’ai démarré LyncPerfTool. exe, mais rien ne se passe. Que se passe-t-il?

Vérifiez le compteur total de points de terminaison actifs sur les clients pour voir si les utilisateurs se connectent. Si les utilisateurs ne se connectent pas, vérifiez votre configuration de Lync Server 2013. Ce problème se produit généralement lorsque le nom du serveur, le préfixe d’utilisateur ou le mot de passe est incorrect. Notez que les clients externes doivent spécifier le proxy d’accès comme valeur TargetServer. Vérifiez le port dans le fichier de configuration.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>Comment savoir si un événement se produit?

Les différents compteurs de performance LyncPerfTool indiquent si les utilisateurs se connectent et exécutent des actions. Toutefois, une méthode simple pour vérifier consiste à se connecter à l’un des comptes à l’aide de Lync 2013 et à effectuer l’action souhaitée.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>J’ai installé les outils de planification de capacité de Live Communications Server 2007 R2 et/ou Lync Server 2010. C’est tout!

Non. Il existe des problèmes d’interopérabilité et vous devez désinstaller toutes les versions précédentes de ce produit.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Les outils de stress et de performance configureront-ils la topologie du serveur des informations d’appel CAA?

Non. Les outils créent uniquement des utilisateurs, des contacts et des listes de distribution et simulent la charge des utilisateurs.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Quel est le nombre maximal d’utilisateurs pris en charge par les outils?

Nous avons créé un total de 80 000 utilisateurs et des tests exécutés totalisant 30 000 utilisateurs, à l’aide de ces outils. Nous vous suggérons d’utiliser un maximum de 120 000 utilisateurs, même si les limitations techniques autorisent une plus grande valeur, en fonction du matériel du serveur et du serveur disponibles.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

