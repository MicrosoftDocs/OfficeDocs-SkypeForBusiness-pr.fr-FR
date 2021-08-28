---
title: FAQ sur l Skype Entreprise Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype Entreprise 2015 stress and performance tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifieing comportements you may see when running the Stress and Performance tools.
ms.openlocfilehash: 42fdf53965e190e98e716df0780eac04565d0767
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611933"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>FAQ sur l Skype Entreprise Server 2015 Stress and Performance Tool
 
Skype Entreprise 2015 stress and performance tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifieing comportements you may see when running the Stress and Performance tools.
  
 Ce FAQ couvre certaines des questions les plus fréquemment posées sur l’outil stress and performance Skype Entreprise Server 2015, et peut vous aider à résoudre les problèmes et à choisir la configuration des outils.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Puis-je exécuter LyncPerfTool.exe production ?

Cela **n’est** pas recommandé. L’outil aura un impact sur les performances, la sécurité et l’expérience utilisateur final de votre serveur de production.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Je connecte mes utilisateurs pour la première fois. Pourquoi mes serveurs exécutent-ils une charge élevée ?

La première fois que les utilisateurs se connectent, des opérations supplémentaires se produisent en arrière-plan. Par conséquent, les performances du serveur Microsoft SQL Server principal peuvent être dégradées. Il est recommandé d’exécuter un court test qui connecte tous vos utilisateurs, puis de redémarrer les clients avant de commencer à mesurer les résultats avec l’outil. Skype Entreprise Server ne prend pas en charge plus de 12 sessions d’ouverture de session utilisateur simultanées par seconde, mais sachez que le nombre réel qui peut être géré par vos serveurs dépend de votre configuration matérielle et peut être inférieur à la valeur prise en charge.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Mes clients sont à court de mémoire ! Que dois-je faire ?

Si les clients sont à court de mémoire, vous devez réduire le nombre d’utilisateurs connectés par Skype Entreprise Server pool frontal. Vous pouvez également choisir de mettre à l’échelle les pools frontux si le problème est persistant.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Puis-je exécuter cet outil sur un serveur Skype Entreprise, lui-même ?

Vous ne devez pas le faire. Ce scénario n’est pas pris en charge car il peut échouer en raison d’une insaluration binaire, et aussi parce que l’objectif est de mesurer la consommation des ressources sur le serveur. En fait, l’exécution de l’outil aurait un impact sur les performances du serveur et invaliderait vos données et mesures.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Puis-je LyncPerfTool.exe sur un serveur virtuel ou sur Microsoft Hyper-V Server 2008/2012 ?

Si, tu peux.
  
## <a name="what-does-mpop-mean"></a>Que signifie MPOP ?

MPOP est une manière abrégée de dire « plusieurs points de présence ». MPOP est conçu pour simuler des scénarios où les utilisateurs sont connectés à un client Skype Entreprise 2015 à partir de plusieurs ordinateurs ou périphériques. Sachez que, dans LyncPerfTool.exe, chaque point de terminaison utilise le profil par défaut. En d’autres termes, le profil n’est pas réparti entre deux points de présence.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>J’ai commencé LyncPerfTool.exe mais rien ne se passe. Que se passe-t-il ?

Vérifiez le compteur Nombre total de points de terminaison actifs sur les serveurs pour voir si les utilisateurs se connectent. Si les utilisateurs ne se connectent pas, vérifiez votre configuration Skype Entreprise Server 2015. Le problème que vous voyez se produit généralement parce qu’un nom de serveur, un préfixe d’utilisateur ou un mot de passe est incorrect. Notez que les clients externes doivent spécifier les valeurs Proxy d’accès et TargetServer. Vérifiez le numéro de port dans le fichier de configuration.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Comment puis-je être sûr que quelque chose est mesuré ?

Il existe des compteurs de performance LyncPerfTool qui indiquent si les utilisateurs se connectent et effectuent des actions, mais le moyen le plus simple de s’assurer que les actions sont mesurées consiste à se connecter à l’un des comptes avec un client Skype Entreprise 2015 et à effectuer ces actions vous-même. Vérifiez les résultats pour vérifier que les mesures ont été effectuées.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>J’ai installé les outils de planification de la capacité de Lync Server 2010 et/ou Lync Server 2013. Est-ce normal ?

 Ces outils ont des problèmes d’interopérabilité ! Vous devez désinstaller toutes les versions précédentes de ces outils pour obtenir des données valides à partir de l’outil Stress and Performance Skype Entreprise Server 2015.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Les outils Stress and Performance vont-ils configurer la topologie du serveur d’informations d’appel de l’ACA ?

Non, les outils ne le font pas. Les outils créent uniquement des utilisateurs, des contacts et des listes de distribution pour simuler la charge utilisateur.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Quel est le nombre maximal d’utilisateurs que les outils supportent ?

Lors des tests, nous avons créé jusqu’à 80 000 utilisateurs au total, et exécuté des tests pour un total de 30 000 utilisateurs exécutant ces outils. Nous vous suggérons un maximum de 120 000 utilisateurs, bien que les limitations techniques autorisent des valeurs supérieures. N’oubliez pas que ces valeurs dépendent du serveur et du matériel de votre environnement.
  

