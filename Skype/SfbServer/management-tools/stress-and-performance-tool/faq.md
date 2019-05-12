---
title: Forum aux questions concernant la Skype pour Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype pour Business 2015 Stress and Performance Tool Forum aux questions (FAQ), utiles pour découvrir les configurations de l’outil sont pris en charge, outil de dépannage et clarifier les comportements que vous pouvez rencontrer lors de l’exécution des outils de Stress and Performance .
ms.openlocfilehash: 604644d5aecb12f94304d1c7ce271c68208e1964
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906745"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Forum aux questions concernant la Skype pour Business Server 2015 Stress and Performance Tool
 
Skype pour Business 2015 Stress and Performance Tool Forum aux questions (FAQ), utiles pour découvrir les configurations de l’outil sont pris en charge, outil de dépannage et clarifier les comportements que vous pouvez rencontrer lors de l’exécution des outils de Stress and Performance .
  
 Cette Foire aux questions décrit certaines des questions fréquemment posées sur la Skype pour Business Server 2015 Stress and Performance tool et pouvant vous aider à la résolution des problèmes et l’outil de choix de configuration.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Puis-je exécuter LyncPerfTool.exe en production ?

Il n’est **pas** recommandée. L’outil aurait un impact sur les performances de votre serveur de production, la sécurité et l’expérience utilisateur final.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Je suis session mes utilisateurs pour la première fois. Pourquoi mes serveurs exécutent une charge élevée ?

La première fois qu’ils ouvrent une session, effectuer les opérations supplémentaires en arrière-plan. Par conséquent, les performances sur le Microsoft SQL Server le serveur principal peuvent se dégrader. Il est recommandé que vous exécutez un test court qui se connecte sur tous vos utilisateurs et puis redémarrez les ordinateurs clients avant de commencer à mesurer les résultats avec l’outil. Skype pour Business Server ne prend en charge plus de 12 ouvertures de sessions utilisateur simultanées par seconde, mais sachez le nombre réel qui peut être géré par vos serveurs dépend de votre configuration matérielle et peut être inférieur à la valeur pris en charge.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Mes clients exécutent mémoire insuffisante ! Que dois-je faire ?

Si les clients exécutent mémoire insuffisante, vous devez réduire le nombre d’utilisateurs connectés par Skype pour Business Server un pool frontal. Vous pouvez également choisir à l’échelle avant pools frontaux si le problème est persistant.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Puis-je exécuter cet outil sur un Skype pour Business server, lui-même ?

Vous ne devez pas le faire. Ce scénario n’est pas pris en charge, car il peut échouer en raison d’une incompatibilité binaire et également, car l’objectif est de mesurer la consommation des ressources sur le serveur. Réellement il exécutant l’outil aurait un impact sur les performances du serveur et invalider vos données et les mesures.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Puis-je exécuter LyncPerfTool.exe sur un serveur virtuel ou sur Microsoft Hyper-V Server 2008/2012 ?

Si, tu peux.
  
## <a name="what-does-mpop-mean"></a>Que signifie MPOP ?

MPOP constitue un moyen raccourci de dire « plusieurs points de présence ». MPOP est conçu pour simuler des scénarios où utilisateurs sont connectés à Skype pour Business 2015 client à partir de plusieurs ordinateurs ou périphériques. Sachez que, dans LyncPerfTool.exe, chaque point de terminaison utilise le profil par défaut. En d’autres termes, le profil n’est pas partagé entre deux points de présence.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>J’ai commencé LyncPerfTool.exe mais rien ne se passe. Que se passe-t-il ?

Vérifiez le compteur de points de terminaison actifs totale sur les serveurs pour voir si les utilisateurs se connectent. Si les utilisateurs ne sont pas se connecter, vérifiez votre Skype pour la configuration de Business Server 2015. Le problème que vous voyez généralement se produit parce que le nom du serveur, préfixe d’utilisateur ou mot de passe est incorrect. Notez que les clients externes doivent spécifier des valeurs de Proxy d’accès et TargetServer. Vérifiez le numéro de port dans le fichier de configuration.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Comment puis-je être sûr que quelque chose est mesurée ?

Il existe des compteurs de performance LyncPerfTool qui indiquent si les utilisateurs sont connectent et les actions qui s’exécute, mais la plus simple pour vous assurer que les actions sont mesurées consiste à se connecter à un des comptes avec un Skype pour client Business 2015 et ceux actions vous-même. Vérifiez les résultats pour vérifier des mesures ont été effectuées.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Je dispose des outils de planification Lync Server 2010 Capacity et/ou de planification de la capacité de Lync Server 2013 outils sont installés. Est qu’OK ?

 Ces outils présentent des problèmes d’interopérabilité ! Vous devez désinstaller toutes les versions antérieures de ces outils pour obtenir des données valides la Skype pour Business Server Stress 2015 et outil de performances.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Les outils de Stress and Performance définira la topologie de serveur informations d’appels CAA ?

Non, les outils ne sont pas cela. Les outils créent uniquement des utilisateurs, contacts et listes de distribution, pour simuler la charge utilisateur.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Quel est le nombre maximal d’utilisateurs qui prennent en charge par les outils ?

Lors des tests, nous avons créé un maximum de 80 000 utilisateurs et exécuter des tests total de 30 000 utilisateurs qui exécute ces outils. Nous vous suggérons un maximum de 120 000 utilisateurs, bien que les limitations techniques permettant une plus élevés. N’oubliez pas que ces valeurs dépendent sur le serveur et le matériel dans votre environnement.
  

