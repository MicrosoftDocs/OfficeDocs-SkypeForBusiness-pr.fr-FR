---
title: Calculatrice de planification de capacité de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26abf069d7c1686fe8abb804d6de4508ba6333fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Utiliser le calculateur de planification de capacité pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-21_

Le calculateur Microsoft® Lync™ Server 2013 planification de la capacité est disponible en <http://www.microsoft.com/en-us/download/details.aspx?id=36828>téléchargement à l’adresse. Il est conçu pour vous aider à déterminer les besoins en matière de serveurs en fonction du nombre d’utilisateurs et de modalités de communication activées au sein de votre organisation. Vous entrez le profil de votre organisation et la calculatrice fournit des recommandations qui vous aideront à planifier votre topologie.

Les recommandations créées par la calculatrice sont uniquement destinées à la planification. La simulation de charge réelle est nécessaire pour garantir que Lync Server 2013 est correctement configuré. Pour effectuer des tests de stress en utilisant un chargement simulé, utilisez l' [outil de stress et de performances de Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282724).

Une fois que vous avez déterminé le profil d’utilisateur et les modalités d’activation pour vos utilisateurs, il est temps d’utiliser la calculatrice pour planifier le nombre de serveurs, de mémoires et de bande passante dont vous avez besoin. Cette version du calculateur ne fournit pas de recommandations concernant les spécifications des E/S du disque.

Cette calculatrice vient compléter [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) et [Microsoft Lync Server](lync-server-2013-planning.md). Utilisez le calculateur après avoir consulté le guide et créé une topologie recommandée à l’aide de l’outil de planification.

Vous pouvez tirer pleinement parti du calculateur si vous avez des informations précises et détaillées sur votre profil d’utilisateur spécifique. Par exemple, le pourcentage d’utilisateurs pour lesquels la voix est activée, le nombre moyen d’appels par utilisateur et par heure, la durée des appels et le pourcentage d’utilisateurs simultanés dans les conférences peuvent faire une différence considérable en matière de configuration du serveur. La précision des recommandations créées par le calculateur dépend de celle des informations que vous fournissez.

<div>

## <a name="using-the-capacity-calculator"></a>Utilisation du calculateur de capacité

La calculatrice est une feuille de calcul Microsoft Excel®. Les cellules en couleur orange sont des entrées de votre part. Les valeurs par défaut sont tapées (les utilisateurs 80 000 au sein d’un pool avec douze serveurs front-end), mais vous pouvez modifier ces valeurs selon les besoins de votre organisation.

Le modèle d’utilisation contient les sections suivantes. Pour calculer vos exigences de capacité, entrez les données comme décrit ci-dessous :

**Messagerie instantanée et présence**

  - Sous nombre d’utilisateurs, entrez le nombre d’utilisateurs connectés en même temps. Ce nombre représente généralement 80 % du nombre total des utilisateurs approvisionnés. Le plus souvent, 100 % de vos utilisateurs simultanés seront activés pour la messagerie instantanée et la présence. La valeur par défaut est 80 000.

  - Nombre moyen de contacts dans la liste de contacts indique le nombre de contacts utilisé pour valider votre configuration système. Ce numéro ne peut pas être modifié.

**Voix Entreprise**

  - Dans utilisateurs activés pour voix entreprise, tapez le pourcentage d’utilisateurs activés pour voix entreprise. La valeur par défaut est 60 %.

  - En fonction du nombre d’appels par utilisateur et par heure (PIC), tapez le nombre d’appels par heure que vous vous attendez à ce que l’utilisateur moyen de participer au cours de la période de pointe. La valeur par défaut est 4.

  - Dans Pourcentage d’appels qui contournent le trafic multimédia, tapez le pourcentage des appels passés par vos utilisateurs qui contourneront le serveur de médiation. La valeur par défaut est 65%.

  - Dans Pourcentage d’utilisateurs de la voix participant à des appels UC-PSTN, tapez le pourcentage des appels de votre organisation qui sont des appels téléphoniques UC-PSTN. La valeur par défaut est 60%

  - Dans le pourcentage d’utilisateurs vocaux impliqués dans les appels de communications unifiées, indique le pourcentage d’utilisateurs qui sont activés pour les voix d’entreprise, qui seront activés uniquement pour les appels UC par UC. Ce nombre est calculé sur la base de la valeur que vous avez entrée dans le champ Pourcentage d’utilisateurs de la voix activés pour les appels UC-RTC.

**Conférence**

  - En pourcentage d’utilisateurs dans les conférences simultanées, tapez le pourcentage d’utilisateurs qui participeront simultanément à des conférences. La valeur par défaut est 5 %.

  - Dans le pourcentage de conférences d’une conversation de groupe (pas de voix), tapez le pourcentage de conférences dont les conférences n’impliquent que la messagerie instantanée. autrement dit, il n’y a pas de composant audio. La valeur par défaut est 10 %.

  - En pourcentage d’utilisateurs à l’aide de la fonction de conférence rendez-vous, tapez le pourcentage de participants concurrents en conférences qui utiliseront la Conférence rendez-vous. La valeur par défaut est 15 %.

  - Dans pourcentage de conférences utilisant la voix, tapez le pourcentage de conférences qui incluront un composant audio.
    
      - Si 20 % de vos conférences vocales incluront également de la vidéo standard, activez la case à cocher Vidéo incluse (pas de multi-vue).
    
      - Si 20 % de vos conférences incluront également la vidéo multi-vue, activez la case à cocher Multi-vue incluse.
    
      - Si 50 % de vos conférences vocales incluront également le partage d’application, activez la case à cocher Partage d’application inclus.
    
      - Si 20% de vos conférences vocales incluent des téléchargements de données, tels que Microsoft PowerPoint® présentations, activez la case à cocher inclure les conférences Web.

**Mobilité**

  - Dans pourcentage d’utilisateurs activés pour la mobilité, tapez le pourcentage d’utilisateurs qui seront activés pour se connecter à Lync Server à l’aide d’appareils mobiles. La valeur par défaut est 40 %.

Lorsque vous avez entré toutes les informations nécessaires, le calculateur de capacité évalue votre configuration requise. Les cellules jaunes montrent des valeurs calculées pour le processeur, la mémoire et les exigences de bande passante en fonction des tests exécutés dans Lync Server 2013 performance Labs. Les nombres sont fournis dans le cadre d’une instruction, et aucune variante unique n’est testée et validée. Les valeurs suivantes sont calculées :

  - PROCESSEUR frontal : pourcentage d’utilisation de l’UC si le chargement complet a été géré par un serveur frontal de mêmes spécifications que le serveur utilisé dans les tests Microsoft.

  - Réseau (Mbits/s) : bande passante requise en mégabits par seconde (Mbits/s) pour la charge de travail correspondante.

  - Mémoire (Go) : mémoire requise en giga-octets (Go) pour la charge de travail correspondante.

Les cellules vertes indiquent les recommandations pour le modèle d’utilisation que vous avez entré.

  - Nombre total de serveurs frontaux : le nombre de serveurs physiques requis est basé sur des serveurs dédiés exécutant Lync Server 2013 avec deux processeurs, avec le cœur hexadécimal, avec 2 260 mégacycles.

  - Il est recommandé d’activer l’hyperthreading. Il a été démontré que cette technologie améliore les performances des serveurs prenant en charge le son et la vidéo.

  - Serveurs Edge : le nombre de serveurs Edge requis, en fonction de 30% de tous les utilisateurs concurrents qui communiquent par le biais des serveurs Edge. Ce pourcentage ne peut pas être modifié dans la calculatrice.

  - Magasin pour l’archivage/l’enregistrement des détails des appels/les services de qualité de l’expérience (QoE) : nombre de magasins requis pour les fonctionnalités d’archivage ou de surveillance, si celles-ci sont activées dans votre organisation.

  - Serveur de base de données principal requis (pools requis) : nombre de serveurs de base de données principaux requis pour prendre en charge la charge de travail sélectionnée.

Dans la ligne en regard de Nombre total de serveurs frontaux, des informations supplémentaires sont fournies sur la charge sur vos serveurs et le réseau pour les charges de travail combinées.

  - Charge processeur moyenne : utilisation moyenne du processeur par serveur frontal.

  - Réseau (en Mbits/s) : allocation de bande passante requise pour prendre en charge le modèle d’utilisation que vous avez entré.

  - Mémoire (en Go) : mémoire en giga-octets requise pour chaque serveur frontal.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Ajustement de vos processeurs

Tous les chiffres relatifs à l’utilisation du processeur dans la feuille de calcul partent du principe que chaque serveur est équipé d’un biprocesseur, hexa-cœur avec 2,26 GHz, 32 Go de mémoire au minimum, et 8 (ou plus) disques durs d’une vitesse de 10 000 RPM avec au moins 72 Go d’espace disponible.

Si vos serveurs ont d’autres processeurs, vous pouvez modifier les chiffres pour les adapter à votre matériel.

</div>

</div>

<span> </span>

</div>

</div>

</div>

