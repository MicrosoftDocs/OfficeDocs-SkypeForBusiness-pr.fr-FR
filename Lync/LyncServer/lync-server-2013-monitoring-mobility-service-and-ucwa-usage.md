---
title: Surveillance de l’utilisation du service de mobilité et UCWA
TOCTitle: Surveillance de l’utilisation du service de mobilité et UCWA
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690025(v=OCS.15)
ms:contentKeyID: 49297928
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Surveillance de l’utilisation du service de mobilité et UCWA

 

_**Dernière rubrique modifiée :** 2013-02-14_

Il convient de surveiller régulièrement l’utilisation de la mémoire et du processeur par le service de mobilité de Lync Server (Mcx) et l’API web de communications unifiées (UCWA). Pour cela, vous pouvez utiliser l’un des éléments suivants :

**Pour l’API web de communications unifiées (UCWA) :**

  - le processus de travail **LyncUcwa** dans Gestionnaire des services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;

  - les compteurs de performances **UC** et **Processeur**.

Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 pour cent. L’utilisation de la mémoire doit être dans les limites décrites dans [Surveillance des limites de capacité de mémoire des serveurs](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :

  - **LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, qui indique le nombre de demandes web en attente sur le serveur. Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».

  - **ASP.NET\\Requests Queued** (doit toujours être égal à zéro).

> [!NOTE]  
> Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.

**Pour le service de mobilité (Mcx) :**

  - les processus de travail **CSIntMcxAppPool** et **CSExtMcxAppPool** dans Gestionnaire des services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;

  - les compteurs de performances **UC** et **Processeur**.

Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 pour cent. L’utilisation de la mémoire doit être dans les limites décrites dans [Surveillance des limites de capacité de mémoire des serveurs](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :

  - **ASP.NET v2.0.50727\\Requests Current**, qui indique le nombre de demandes web en attente sur le serveur. Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».

  - **ASP.NET\\Requests Queued** (doit toujours être égal à zéro).

> [!NOTE]  
> Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.

## Voir aussi

#### Concepts

[Surveillance des limites de capacité de mémoire des serveurs](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

