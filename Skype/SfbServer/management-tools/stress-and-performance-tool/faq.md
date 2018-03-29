---
title: Forum aux questions concernant la Skype pour Business Server 2015 Stress et l’outil performances
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype pour entreprise 2015 Stress et l’outil performances questions fréquemment posées (FAQ), utiles pour savoir quelles configurations de l’outil sont pris en charge, résolution des problèmes de l’outil et clarifier les comportements que vous pouvez rencontrer lors de l’exécution des outils de contrainte et de performances .
ms.openlocfilehash: 730f9620e4aa498df26cc24f3c17ea1bd2ad7d5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Forum aux questions concernant la Skype pour Business Server 2015 Stress et l’outil performances
 
Skype pour entreprise 2015 Stress et l’outil performances questions fréquemment posées (FAQ), utiles pour savoir quelles configurations de l’outil sont pris en charge, résolution des problèmes de l’outil et clarifier les comportements que vous pouvez rencontrer lors de l’exécution des outils de contrainte et de performances .
  
 Ce forum aux questions répond aux questions les plus fréquemment posées sur le Skype pour outil Business Server 2015 Stress et des performances et peut aider à la résolution des problèmes et l’outil de choix de configuration.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Puis-je exécuter LyncPerfTool.exe en production ?

Ce n’est **pas** recommandée. L’outil aurait un impact sur les performances de votre serveur de production, la sécurité et l’expérience de l’utilisateur final.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Je suis session mes utilisateurs pour la première fois. Pourquoi mes serveurs fonctionnent à une charge élevée ?

La première fois qu’ils ouvrent une session, les opérations supplémentaires se produisent en arrière-plan. En conséquence, les performances sur le Microsoft SQL Server serveur principal peuvent être altérées. Il est recommandé que vous exécutez un test court qui se connecte sur tous vos utilisateurs et puis redémarrez les ordinateurs clients avant de commencer à mesurer les résultats à l’aide de l’outil. Skype pour Business Server ne prend en charge de plus de 12 sessions d’ouverture de session utilisateur simultanées par seconde, mais soyez conscient que le nombre réel qui peut être géré par vos serveurs dépend de votre configuration matérielle et peut être inférieur à la valeur prise en charge.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Mes clients utilisent plus de mémoire ! Que dois-je faire ?

Si les clients utilisent plus de mémoire, vous devez réduire le nombre d’utilisateurs connectés par Skype pour le pool d’entreprise serveur frontal. Vous pouvez également choisir de mettre à l’échelle avant de pools de fin si le problème est persistant.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Puis-je exécuter cet outil sur un Skype pour Business server, lui-même ?

Vous ne devez pas le faire. Ce scénario n’est pas pris en charge, car il peut échouer en raison d’une incompatibilité binaire et également, car l’objectif est de mesurer la consommation de ressources sur le serveur. En exécutant l’outil il aurait un impact sur les performances du serveur et invalider vos données et les mesures.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Puis-je exécuter LyncPerfTool.exe sur un serveur virtuel ou sur Microsoft Hyper-V Server 2008/2012 ?

Si, tu peux.
  
## <a name="what-does-mpop-mean"></a>Que signifie MPOP ?

MPOP est une façon abrégée de dire « plusieurs points de présence ». MPOP est conçu pour simuler des scénarios où les utilisateurs sont connectés à Skype pour client d’entreprise 2015 depuis plusieurs ordinateurs ou périphériques. N’oubliez pas que, dans LyncPerfTool.exe, chaque point de terminaison utilise le profil par défaut. En d’autres termes, le profil n’est pas divisé entre deux points de présence.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Démarrage de la LyncPerfTool.exe, mais rien ne se passe. Que se passe-t-il ?

Vérifiez le compteur de points de terminaison actifs Total sur les serveurs pour voir si les utilisateurs se connectent. Si les utilisateurs ne sont pas vous connecter, vérifiez votre Skype pour la configuration de Business Server 2015. Le problème que vous voyez généralement se produit parce que le nom du serveur, préfixe d’utilisateur ou mot de passe est incorrect. Notez que les clients externes doivent spécifier des valeurs de TargetServer et Proxy d’accès. Vérifiez le numéro de port dans le fichier de configuration.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Comment puis-je être sûr que quelque chose est mesurée ?

Il existe des compteurs de performances LyncPerfTool qui indiquent si les utilisateurs se connectent et exécution des actions, mais la façon la plus simple pour vous assurer que les actions sont mesurées consiste à ouvrir une session sur un des comptes avec un Skype pour client d’entreprise 2015 et ceux actions vous-même. Vérifiez les résultats pour confirmer les mesures ont été prises.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>J’ai des outils de planification de capacité Lync Server 2010 ou de planification de capacité de Lync Server 2013 outils installés. Est-ce OK ?

 Ces outils ont des problèmes d’interopérabilité ! Vous devez désinstaller toutes les versions antérieures de ces outils pour obtenir des données valides de le Skype pour Business Server 2015 Stress et l’outil performances.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Les outils de Performance et de Stress définit la topologie de serveur TCHA informations d’appels ?

Non, les outils ne sont pas cela. Les outils de créent uniquement des utilisateurs, contacts et listes de distribution, pour simuler la charge utilisateur.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Quel est le nombre maximal d’utilisateurs pris en charge par les outils ?

Lors des tests, nous avons créé un total de 80 000 utilisateurs et l’exécution de tests total de 30 000 utilisateurs exécutant ces outils. Nous suggérons un maximum de 120 000 utilisateurs, bien que les limites techniques permettent une valeur plus élevée. N’oubliez pas que ces valeurs dépendent sur le serveur et le matériel de votre environnement.
  

