---
title: Forum aux questions sur l’outil de contrainte et de performances de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445448633bc35b8071455ccd0c8e6ff93c3862b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509211"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Forum aux questions sur l’outil de contrainte et de performances de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Foire aux questions

Voici quelques questions fréquemment posées sur l’outil de contrainte et de performances de Lync Server 2013.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>Puis-je exécuter LyncPerfTool.exe en production ?

Nous vous déconseillons de le faire. Cet outil aura un impact sur les performances, la sécurité et l’expérience utilisateur du serveur.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>Je me connecte pour la première fois. Pourquoi les serveurs fonctionnent-ils à cette charge élevée ?

La première fois que les utilisateurs se connectent, des opérations supplémentaires se produisent. Par conséquent, les performances du serveur principal Microsoft SQL Server seront dégradées. Nous vous recommandons d’exécuter un test court qui ouvre une session sur tous les utilisateurs, puis de redémarrer les clients avant de mesurer les résultats. Nous ne prenons pas en charge plus de 12 sessions de connexion utilisateur simultanées par seconde, mais cela dépend de votre configuration matérielle.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Mes clients manquent de mémoire. Que dois-je faire ?

Si la mémoire de vos clients est insuffisante, vous devez réduire le nombre d’utilisateurs par ordinateur.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>Mon client dispose d’un processeur de 100% en tout temps. Que dois-je faire ?

Si vos clients s’exécutent avec un processeur très élevé une fois que tous les utilisateurs ont ouvert une session, vous devez réduire le nombre d’utilisateurs par ordinateur. Les pics d’utilisation du processeur élevés sont acceptables, mais si elle est soutenue, vous devez réduire la charge.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>Puis-je exécuter l’outil sur le serveur lui-même ?

Non. Ce scénario n’est pas pris en charge et peut échouer en raison d’une incompatibilité binaire. En outre, étant donné que le point est de mesurer la consommation des ressources sur le serveur, l’exécution de l’outil peut rendre les mesures sans signification.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Puis-je exécuter LyncPerfTool.exe sur un serveur virtuel ou sur Microsoft Hyper-V Server 2008/2012 ?

Oui.

</div>

<div>

## <a name="what-does-mpop-mean"></a>Qu’est-ce que MPOP signifie ?

MPOP signifie plusieurs points de présence. Il est conçu pour simuler le scénario dans lequel les utilisateurs sont connectés à Lync 2013 à partir de plusieurs machines. Notez que dans LyncPerfTool.exe, chaque point de terminaison utilise le profil par défaut (autrement dit, le profil n’est pas fractionné entre les deux points de présence).

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>J’ai commencé LyncPerfTool.exe mais rien ne se passe. Que se passe-t-il ?

Vérifiez le compteur nombre total de points de terminaison actifs sur les clients pour voir si les utilisateurs se connectent. Si les utilisateurs ne se connectent pas, vérifiez votre configuration Lync Server 2013. Ce problème se produit généralement lorsque le nom du serveur, le préfixe d’utilisateur ou le mot de passe est incorrect. Notez que les clients externes doivent spécifier le proxy d’accès comme valeur de TargetServer. Vérifiez le port dans le fichier de configuration.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>Comment puis-je savoir ce qu’il se passe ?

Les différents compteurs de performance LyncPerfTool indiquent si les utilisateurs se connectent et exécutent des actions. Toutefois, il est facile de vérifier qu’il est possible de se connecter à l’un des comptes à l’aide de Lync 2013 et d’effectuer l’action souhaitée.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Les outils de planification de capacité de Live Communications Server 2007 R2 et/ou Lync Server 2010 sont installés. Est-ce OK ?

Non. Il existe des problèmes d’interopérabilité et vous devez désinstaller toutes les versions précédentes de ce produit.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Les outils de stress et de performances configurent-ils la topologie du serveur d’informations d’appel CAA ?

Non. Les outils créent uniquement des utilisateurs, des contacts et des listes de distribution et simulent la charge utilisateur.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Quel est le nombre maximal d’utilisateurs pris en charge par les outils ?

Nous avons créé un total de 80 000 utilisateurs et des tests exécutés totalisant 30 000 utilisateurs, à l’aide de ces outils. Nous vous suggérons un maximum de 120 000 utilisateurs, même si les limitations techniques permettent une plus grande valeur, en fonction du matériel du client et du serveur disponible.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

