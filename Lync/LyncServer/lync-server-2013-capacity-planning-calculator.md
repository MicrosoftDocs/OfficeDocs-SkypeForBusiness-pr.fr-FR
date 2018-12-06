---
title: Utilisation du calculateur de planification de la capacité de Lync Server 2013
TOCTitle: Utilisation du calculateur de planification de la capacité de Lync Server 2013
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56269672
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation du calculateur de planification de la capacité de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le calculateur de planification de la capacité Microsoft® Lync™ Server 2013 peut être téléchargé à l’adresse <http://www.microsoft.com/en-us/download/details.aspx?id=36828>. Il est conçu pour vous aider à déterminer la configuration de serveur requise selon le nombre d’utilisateurs et les modalités de communication activées au niveau de votre organisation. Il vous suffit d’entrer le profil de votre organisation pour que le calculateur fournisse des recommandations qui vous aident à planifier votre topologie.

Les recommandations créées par le calculateur servent à des fins de planification uniquement. Une simulation de charge réelle est requise pour garantir que Lync Server 2013 est correctement configuré. Pour effectuer des tests de contrainte sous une charge simulée, utilisez l’[outil de test de contrainte et de performances de Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282724).

Une fois que vous avez déterminé votre profil d’utilisateur et les modalités que vous voulez activer pour vos utilisateurs, vous devez utiliser le calculateur pour planifier le nombre de serveurs, la quantité de mémoire et la bande passante dont vous avez besoin. Cette version du calculateur ne fournit pas de recommandations en matière d’E/S disque requis.

Ce calculateur vient compléter l’[outil de planification de Microsoft Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282725) et le [processus de planification de Microsoft Lync Server](lync-server-2013-planning.md). Utilisez le calculateur après avoir consulté le guide et créé une topologie recommandée à l’aide de l’outil de planification.

Vous pouvez tirer pleinement parti du calculateur si vous avez des informations précises et détaillées sur votre profil d’utilisateur spécifique. Par exemple, le pourcentage d’utilisateurs pour lesquels la voix est activée, le nombre moyen d’appels par utilisateur et par heure, la durée des appels et le pourcentage d’utilisateurs simultanés dans les conférences peuvent faire une différence considérable en matière de configuration du serveur. La précision des recommandations créées par le calculateur dépend de celle des informations que vous fournissez.

## Utilisation du calculateur de capacité

Le calculateur est une feuille de calcul Microsoft Excel®. Les cellules oranges vous permettent d’entrer des valeurs. Des valeurs par défaut sont entrées (80 000 utilisateurs dans un pool avec douze serveurs frontaux). Vous pouvez modifier celles-ci selon les besoins de votre organisation.

Le modèle d’utilisation contient les sections suivantes. Pour calculer la capacité requise, entrez les données en suivant les instructions :

**Messagerie instantanée et présence**

  - Sous Nombre d’utilisateurs, tapez le nombre d’utilisateurs qui seront connectés simultanément. Ce nombre représente généralement 80 % du nombre total des utilisateurs approvisionnés. Le plus souvent, 100 % de vos utilisateurs simultanés seront activés pour la messagerie instantanée et la présence. La valeur 80 000 est définie par défaut.

  - Nombre moyen de contacts dans la liste de contacts indique le nombre de contacts utilisé pour valider votre configuration système. Ce nombre n’est pas modifiable.

**Voix Entreprise**

  - Dans Utilisateurs activés pour Voix Entreprise, tapez le pourcentage de vos utilisateurs qui sont activés pour Voix Entreprise. La valeur par défaut est 60 %.

  - Dans Nombre moyen d’appels par utilisateur et par heure (pic), tapez le nombre d’appels par heure auxquels vous estimez que l’utilisateur moyen participera pendant les heures de pointe. La valeur par défaut est 4.

  - Dans Pourcentage d’appels qui utilisent le contournement de média, tapez le pourcentage d’appels passés par vos utilisateurs qui contourneront le serveur de médiation. La valeur par défaut est 65 %.

  - Dans Pourcentage d’utilisateurs de la voix participant à des appels UC-PSTN, tapez le pourcentage des appels de votre organisation qui sont des appels téléphoniques UC-PSTN. La valeur par défaut est 60 %

  - Dans Pourcentage d’utilisateurs de la voix participant à des appels UC-UC indique le pourcentage d’utilisateurs activés pour Voix Entreprise qui ne pourront que passer et recevoir des appels UC-UC. Ce nombre est calculé sur la base de la valeur que vous avez entrée dans le champ Pourcentage d’utilisateurs de la voix activés pour les appels UC-PSTN.

**Conférence**

  - Dans Pourcentage d’utilisateurs dans des conférences simultanées, tapez le pourcentage d’utilisateurs qui participeront simultanément à des conférences. La valeur par défaut est 5 %.

  - Dans Pourcentage de conférences avec la messagerie instantanée de groupe uniquement (pas de voix), tapez le pourcentage de conférences qui impliqueront la messagerie instantanée uniquement (sans composant audio). La valeur par défaut est 10 %

  - Dans Pourcentage d’utilisateurs utilisant les conférences rendez-vous, tapez le pourcentage de participants simultanés dans des conférences qui utiliseront les conférences rendez-vous. La valeur par défaut est 15 %.

  - Dans Pourcentage de conférences utilisant la voix, tapez le pourcentage de conférences qui incluront un composant audio.
    
      - Si 20 % de vos conférences vocales incluront également de la vidéo standard, activez la case à cocher Vidéo incluse (pas de multi-vue).
    
      - Si 20 % de vos conférences incluront également la vidéo multi-vue, activez la case à cocher Multi-vue incluse.
    
      - Si 50 % de vos conférences vocales incluront également le partage d’application, activez la case à cocher Partage d’application inclus.
    
      - Si 20 % de vos conférences vocales incluront des téléchargements de données, tels que des présentations Microsoft PowerPoint®, activez la case à cocher Conférence web incluse.

**Mobilité**

  - Dans Pourcentage d’utilisateurs activés pour la mobilité, tapez le pourcentage de vos utilisateurs qui seront activés pour se connecter à Lync Server à l’aide d’appareils mobiles. La valeur par défaut est 40 %.

Lorsque vous avez entré toutes les informations nécessaires, le calculateur de capacité estime la configuration requise. Les cellules jaunes montrent les valeurs calculées pour le processeur, la mémoire et la bande passante sur la base des tests effectués au sein des laboratoires de performance Lync Server 2013. Les nombres sont fournis à titre indicatif. Toutes les variations possibles n’ont pas été testées et validées. Les valeurs suivantes sont calculées :

  - Processeur du serveur frontal : pourcentage d’utilisation du processeur si la charge entière était gérée par un serveur frontal avec les mêmes spécifications que le serveur utilisé dans les tests effectués par Microsoft.

  - Réseau (Mbits/s) : bande passante requise en mégabits par seconde (Mbits/s) pour la charge de travail correspondante.

  - Mémoire (Go) : mémoire requise en giga-octets (Go) pour la charge de travail correspondante.

Les cellules vertes indiquent les recommandations pour le modèle d’utilisation que vous avez entré.

  - Nombre total de serveurs frontaux : le nombre de serveurs physiques requis est basé sur les serveurs dédiés exécutant Lync Server 2013 avec biprocesseur, hexa-cœur et 2 260 mégacycles.

  - Il est recommandé d’activer l’hyperthreading. Il a été démontré que cette technologie améliore les performances des serveurs prenant en charge le son et la vidéo.

  - Serveurs Edge : nombre de serveurs Edge requis, sur la base de 30 % de tous les utilisateurs communiquant simultanément via les serveurs Edge. Ce pourcentage ne peut pas être modifié dans le calculateur.

  - Magasin pour l’archivage/l’enregistrement des détails des appels/les services de qualité de l’expérience (QoE) : nombre de magasins requis pour les fonctionnalités d’archivage ou de surveillance, si celles-ci sont activées dans votre organisation.

  - Serveur de base de données principal requis (pools requis) : nombre de serveurs de base de donnés principaux requis pour prendre en charge la charge de travail sélectionnée.

Dans la ligne en regard de Nombre total de serveurs frontaux, des informations supplémentaires sont fournies sur la charge sur vos serveurs et le réseau pour les charges de travail combinées.

  - Charge processeur moyenne : utilisation moyenne du processeur par serveur frontal.

  - Réseau (en Mbits/s) : allocation de bande passante requise pour prendre en charge le modèle d’utilisation que vous avez entré.

  - Mémoire (en Go) : mémoire en giga-octets requise pour chaque serveur frontal.

## Ajustement de vos processeurs

Tous les chiffres relatifs à l’utilisation du processeur dans la feuille de calcul partent du principe que chaque serveur est équipé d’un biprocesseur, hexa-cœur avec 2,26 GHz, 32 Go de mémoire au minimum, et 8 (ou plus) disques durs d’une vitesse de 10 000 RPM avec au moins 72 Go d’espace disponible.

Si vos serveurs ont d’autres processeurs, vous pouvez modifier les chiffres pour les adapter à votre matériel.

