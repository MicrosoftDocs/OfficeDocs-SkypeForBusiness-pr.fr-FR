---
title: Surveillance des limites de capacité de mémoire des serveurs
TOCTitle: Surveillance des limites de capacité de mémoire des serveurs
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh689982(v=OCS.15)
ms:contentKeyID: 49296369
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Surveillance des limites de capacité de mémoire des serveurs

 

_**Dernière rubrique modifiée :** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

> [!WARNING]  
> Les informations de cette rubrique au sujet de la planification de la capacité ne concernent que les clients Lync 2010 Mobile et le service de mobilité (Mcx). La planification de la capacité pour l’API UCWA (Unified Communications Web API), utilisée par les clients Lync 2013 Mobile, est fournie par l’outil de planification Lync Server 2013.

Deux compteurs de performances de mobilité peuvent vous aider à déterminer votre utilisation actuelle, à planifier la capacité du service de mobilité Lync Server 2013 (Mcx) et à surveiller l’utilisation de la mémoire pour l’API UCWA. Pour cette dernière, la catégorie de compteurs est **LS:WEB – UCWA**. Pour le service de mobilité (Mcx), les compteurs se trouvent dans la catégorie **LS:WEB - Service de communication mobile**. Les compteurs à surveiller sont les suivants :

  - **Nombre de sessions actives avec abonnements actifs aux informations de présence**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité (Mcx) dont les abonnements aux informations de présence sont actifs (nombre d’utilisateurs mobiles toujours connectés) ;

  - **Nombre de sessions actives**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité.

Si la différence entre les compteurs **Nombre de sessions actives avec abonnements actifs aux informations de présence** et **Nombre de sessions actives** est minime au fil du temps, cela signifie que la plupart des utilisateurs d’appareils mobiles disposent d’un appareil toujours connecté, tel qu’un appareil mobile Android ou Nokia (pour Mcx uniquement). Les appareils UCWA toujours connectés comprennent les appareils Apple et Android exécutant les clients Lync 2013 Mobile). Si le compteur **Nombre de sessions actives** est beaucoup plus élevé que le compteur **Nombre de sessions actives avec abonnements actifs aux informations de présence**, cela indique qu’un nombre plus élevé d’utilisateurs emploient un appareil à points de terminaison en arrière-plan, tel qu’un appareil Apple iOS ou Windows Phone sous Mcx. (Windows Phone est le seul client Lync 2013 Mobile enregistré comme tel).

Il est préférable de définir une limite sur les compteurs de performances **Nombre de sessions actives avec abonnements actifs aux informations de présence** et **Nombre de sessions actives** en fonction de votre utilisation prévue, des résultats de la planification de la capacité et de l’analyse en continu du service de mobilité et d’autres compteurs serveur frontal. Les limites que vous définissez doivent vous permettre d’évaluer la capacité des serveurs et de déclencher des alertes quand celle-ci est dépassée.

Pour déterminer les limites appropriées, vous devez d’abord déterminer la quantité de mémoire disponible sur le serveur frontal du service de mobilité. Surveillez les compteurs afin de déterminer le besoin de prévoir une capacité supplémentaire à l’aide de la formule suivante :

Mémoire totale utilisée par le service de mobilité Mcx (Mo) = 164 + (400 + 134) / 1024 \* **Nombre de sessions actives avec abonnements actifs aux informations de présence** + 400 / 1024 \* (**Nombre de sessions actives** – **Nombre de sessions actives avec abonnements actifs aux informations de présence**)

> [!IMPORTANT]  
> Le calculateur de capacité Microsoft Lync Server 2010 est une feuille de calcul préremplie avec toutes les formules permettant à un planificateur de déterminer les besoins pour les serveurs, notamment en ce qui concerne l’UC, la mémoire et le disque dur. Vous pouvez télécharger la feuille de calcul et un document associé à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=212657" class="uri">http://go.microsoft.com/fwlink/?linkid=212657</a>.

Le serveur frontal a besoin de suffisamment de mémoire disponible pour prendre en charge le service de mobilité en cas de basculement. Vous pouvez contrôler la mémoire actuellement disponible sur le serveur frontal à l’aide du compteur **Mémoire/Mégaoctets disponibles** ou de l’équation mentionnée précédemment pour prévoir la quantité de mémoire utilisée par le service de mobilité.

Si la quantité de mémoire disponible sur le serveur frontal est inférieure à 1 500 Mo lorsque vous planifiez le nombre d’utilisateurs du service de mobilité, vous devez ajouter du matériel afin de prendre en charge le service de mobilité. Pour plus d’informations, voir [Surveillance des performances de mobilité dans Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) dans la documentation des opérations.

## Voir aussi

#### Autres ressources

[Surveillance des performances de mobilité dans Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)

