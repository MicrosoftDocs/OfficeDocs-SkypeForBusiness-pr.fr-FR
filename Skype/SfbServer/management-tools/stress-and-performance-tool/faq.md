---
title: FAQ sur l’outil de stress et de performances de Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Outil de stress et de performance 2015 de Skype entreprise, des questions fréquemment posées (FAQ), qui vous permettent de découvrir les configurations d’outils prises en charge, les problèmes liés aux outils de résolution des problèmes et les comportements de clarification qui peuvent apparaître lors de l’utilisation des outils de stress et de performance .
ms.openlocfilehash: 36bb3e05751bd69b747d84fa563347b29362ddd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299708"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>FAQ sur l’outil de stress et de performances de Skype entreprise Server 2015
 
Outil de stress et de performance 2015 de Skype entreprise, des questions fréquemment posées (FAQ), qui vous permettent de découvrir les configurations d’outils prises en charge, les problèmes liés aux outils de résolution des problèmes et les comportements de clarification qui peuvent apparaître lors de l’utilisation des outils de stress et de performance .
  
 Ce Forum aux questions décrit certaines des questions les plus fréquemment posées sur l’outil de stress et de performance de Skype entreprise Server 2015 et permet de résoudre les problèmes liés aux options de configuration de l’outil.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Est-il possible d’exécuter LyncPerfTool. exe en production?

Cette opération n’est **pas** recommandée. L’outil aura un impact sur les performances de votre serveur de production, la sécurité et l’utilisation de l’utilisateur final.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>J’enregistre mes utilisateurs pour la première fois. Pourquoi mon serveur fonctionne-t-il en charge?

La première fois que les utilisateurs se connectent, des opérations supplémentaires se produisent en arrière-plan. Par conséquent, les performances du serveur principal Microsoft SQL Server peuvent être détériorées. Il est recommandé d’effectuer un test de courte durée de connexion à tous vos utilisateurs, puis de redémarrer les clients avant de commencer à mesurer les résultats avec l’outil. Skype entreprise Server ne prend pas en charge plus de 12 sessions d’ouverture de session simultanées par seconde, mais n’oubliez pas que le nombre réel qui peut être géré par vos serveurs dépend de votre configuration matérielle et peut être inférieur à la valeur prise en charge.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Ma mémoire est insuffisante pour vos clients. Que dois-je faire?

Si les clients manquent de mémoire, vous devez réduire le nombre d’utilisateurs connectés dans le pool frontal Skype entreprise Server. Si le problème persiste, vous pouvez également choisir de mettre à l’échelle les listes frontales.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Est-il possible d’exécuter cet outil sur un serveur Skype entreprise?

Ce n’est pas le cas. Ce scénario n’est pas pris en charge, car il peut échouer en raison d’une incompatibilité binaire, et en raison du fait que l’objectif est de mesurer la consommation de ressources sur le serveur. L’exécution de l’outil est réellement susceptible d’influer sur les performances du serveur et d’invalidité de vos données et de vos mesures.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Est-il possible d’exécuter LyncPerfTool. exe sur un serveur virtuel ou sur Microsoft Hyper-V Server 2008/2012?

Si, tu peux.
  
## <a name="what-does-mpop-mean"></a>Qu’est-ce que MPOP?

MPOP est un moyen raccourci de dire «plusieurs points de présence». MPOP est conçu pour simuler des scénarios où les utilisateurs sont connectés au client Skype entreprise 2015 à partir de plusieurs machines ou périphériques. Sachez que, dans LyncPerfTool. exe, chaque point de terminaison utilise le profil par défaut. En d’autres termes, le profil n’est pas fractionné entre deux points de présence.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>J’ai démarré LyncPerfTool. exe, mais rien ne se passe. Que se passe-t-il?

Vérifiez le compteur total de points de terminaison actifs sur les serveurs pour voir si les utilisateurs se connectent. Si les utilisateurs ne se connectent pas, vérifiez votre configuration de Skype entreprise Server 2015. Le problème que vous rencontrez est généralement dû au fait qu’un nom de serveur, préfixe d’utilisateur ou mot de passe est incorrect. Notez que les clients externes doivent spécifier des valeurs de proxy d’accès et de TargetServer. Vérifiez le numéro de port dans le fichier de configuration.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Comment être sûr d’une mesure?

Il existe d’LyncPerfTool compteurs de performance qui indiquent si des utilisateurs se connectent et exécutent des actions, mais la méthode la plus simple pour vérifier que les actions sont évaluées consiste à vous connecter à l’un des comptes avec un client Skype entreprise 2015 et à effectuer ces opérations. actions vous-même. Vérifiez les résultats pour vérifier les mesures effectuées.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>J’ai installé les outils de planification de capacité de Lync Server 2010 et/ou les outils de planification de capacité de Lync Server 2013. C’est tout!

 Ces outils présentent des problèmes d’interopérabilité. Vous devez désinstaller toutes les versions précédentes de ces outils pour obtenir des données valides dans l’outil de stress et de performances de Skype entreprise Server 2015.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Les outils de stress et de performance configureront-ils la topologie du serveur des informations d’appel CAA?

Non, ce n’est pas le cas pour les outils. Les outils créent uniquement des utilisateurs, des contacts et des listes de distribution pour simuler la charge des utilisateurs.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Quel est le nombre maximal d’utilisateurs pris en charge par les outils?

Lors de l’évaluation, nous avons créé jusqu’à un total d’utilisateurs 80 000, et réalisé des tests de totalisation des utilisateurs 30 000 qui exécutent ces outils. Nous vous suggérons d’utiliser un maximum de 120 000 utilisateurs, même si les limitations techniques autorisent une plus grande valeur. N’oubliez pas que ces valeurs dépendent du serveur et du matériel de votre environnement.
  

