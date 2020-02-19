---
title: Calculatrice de planification de capacité Lync Server 2013
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
ms.openlocfilehash: 0caac7e07d83658fd1b39192a6d9792ae6b17c0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Utilisation de la calculatrice de planification de la capacité pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-21_

La calculatrice de planification de capacité Microsoft® Lync™ Server 2013 peut être téléchargée à l’adresse <https://www.microsoft.com/download/details.aspx?id=36828>. Elle est conçue pour vous aider à déterminer les exigences de serveur en fonction du nombre d’utilisateurs et de modalités de communication activés au sein de votre organisation. Vous entrez le profil de votre organisation et la calculatrice fournit des recommandations pour vous aider à planifier votre topologie.

Les recommandations créées par la calculatrice sont uniquement destinées à la planification. La simulation de charge réelle est nécessaire pour s’assurer que Lync Server 2013 est correctement configuré. Pour effectuer des tests de contrainte sous une charge simulée, utilisez l' [outil de contrainte et de performances de Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=282724).

Une fois que vous avez déterminé votre profil utilisateur et les modalités que vous souhaitez activer pour vos utilisateurs, il est temps d’utiliser la calculatrice pour planifier le nombre de serveurs, la mémoire et la bande passante dont vous avez besoin. Cette version de la calculatrice ne fournit pas d’instructions pour les besoins en e/s disque.

Cette calculatrice complète [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) et [Microsoft Lync Server](lync-server-2013-planning.md). Utilisez la calculatrice une fois que vous avez consulté le guide et créé une topologie recommandée à l’aide de l’outil de planification.

Vous pouvez tirer le meilleur parti de la calculatrice si vous disposez d’informations précises et détaillées sur votre profil utilisateur spécifique. Par exemple, le pourcentage d’utilisateurs à extension vocale, le nombre moyen d’appels par utilisateur et par heure, la durée de l’appel et le pourcentage d’utilisateurs simultanés dans les conférences peuvent faire une très grande différence en termes de serveur. La précision des recommandations créées par la calculatrice dépend de la précision des informations que vous fournissez.

<div>

## <a name="using-the-capacity-calculator"></a>Utilisation de la calculatrice de capacité

La calculatrice est une feuille de calcul Microsoft Excel®. Les cellules colorées en orange sont destinées à des fins de saisie. Les valeurs par défaut sont entrées (80 000 utilisateurs dans un pool avec douze serveurs frontaux), mais vous pouvez modifier ces valeurs en fonction des besoins de votre organisation.

Le modèle d’utilisation contient les sections suivantes. Pour calculer vos besoins en capacité, entrez les données comme décrit :

**Messagerie instantanée et présence**

  - Sous nombre d’utilisateurs, tapez le nombre d’utilisateurs qui seront connectés simultanément. Ce nombre est généralement de 80% du nombre total d’utilisateurs configurés. Dans la plupart des cas, 100% de vos utilisateurs simultanés seront activés pour la messagerie instantanée et la présence. La valeur par défaut est 80 000.

  - Nombre moyen de contacts dans la liste de contacts indique le nombre de contacts que nous utilisons pour valider la configuration système requise. Ce numéro ne peut pas être modifié.

**Voix Entreprise**

  - Dans utilisateurs activés pour voix entreprise, tapez le pourcentage de vos utilisateurs qui sont activés pour voix entreprise. La valeur par défaut est 60%.

  - En nombre moyen d’appels par utilisateur et par heure (PIC), tapez le nombre d’appels par heure pendant lesquels l’utilisateur moyen doit participer pendant les périodes de charge maximale. La valeur par défaut est 4.

  - Dans pourcentage des appels qui utilisent la déviation du trafic multimédia, tapez le pourcentage d’appels passés par vos utilisateurs pour contourner le serveur de médiation. La valeur par défaut est 65%.

  - Dans pourcentage des utilisateurs vocaux impliqués dans les appels UC-PSTN, tapez le pourcentage des appels de votre organisation qui sont des appels de téléphone de communications unifiées. La valeur par défaut est 60%.

  - Pourcentage d’utilisateurs vocaux impliqués dans les appels UC-UC indique le pourcentage d’utilisateurs activés pour voix entreprise qui seront activés uniquement pour les appels UC-UC. Ce nombre est calculé en fonction de ce que vous entrez pour le pourcentage d’utilisateurs vocaux activé pour les appels UC-PSTN.

**Vidéoconférence**

  - Dans pourcentage d’utilisateurs dans des conférences simultanées, tapez le pourcentage d’utilisateurs qui participeront simultanément à des conférences. La valeur par défaut est 5%.

  - Dans pourcentage de conférences avec la messagerie instantanée de groupe uniquement (pas de voix), tapez le pourcentage de conférences dont les conférences impliquent uniquement la messagerie instantanée ; autrement dit, il n’y a pas de composant audio. La valeur par défaut est 10%.

  - Dans pourcentage des utilisateurs qui utilisent la Conférence rendez-vous, tapez le pourcentage de participants simultanés dans les conférences qui utiliseront la Conférence rendez-vous. La valeur par défaut est 15%.

  - Dans pourcentage de conférences à l’aide de la voix, tapez le pourcentage de conférences qui comprendront un composant audio.
    
      - Si 20% de vos conférences vocales incluent également une vidéo normale, activez la case à cocher y compris la vidéo (pas de multi-vue).
    
      - Si 20% de vos conférences incluent également la vidéo multi-vue, activez la case à cocher incluant plusieurs vues.
    
      - Si 50% de vos conférences vocales incluent également le partage d’application, activez la case à cocher inclure le partage d’applications.
    
      - Si 20% de vos conférences vocales incluent des téléchargements de données, tels que des présentations Microsoft PowerPoint®, activez la case à cocher inclure la conférence Web.

**Mobilité**

  - Dans pourcentage d’utilisateurs activés pour la mobilité, tapez le pourcentage de vos utilisateurs qui seront activés pour se connecter à Lync Server à l’aide d’appareils mobiles. La valeur par défaut est 40%.

Une fois que vous avez entré toutes les informations nécessaires, la calculatrice de capacité estime votre configuration requise. Les cellules jaunes affichent les valeurs calculées pour l’UC, la mémoire et les besoins en bande passante en fonction des tests effectués dans les laboratoires de performance Lync Server 2013. Les numéros sont fournis en tant qu’indications, et toutes les variantes ne sont pas testées et validées. Les valeurs suivantes sont calculées :

  - PROCESSEUR frontal : pourcentage d’utilisation de l’UC si la totalité de la charge a été gérée par un serveur frontal des mêmes spécifications que le serveur utilisé dans les tests Microsoft.

  - Réseau en Mbits/s : bande passante requise en mégabits par seconde (Mbits/s) pour la charge de travail correspondante.

  - Mémoire en Go : mémoire requise en gigaoctets (Go) pour la charge de travail correspondante.

Les cellules vertes affichent des recommandations pour le modèle d’utilisation que vous avez entré.

  - Nombre total de serveurs frontaux : le nombre de serveurs physiques requis est basé sur des serveurs dédiés exécutant Lync Server 2013 avec deux processeurs, hex-Core, avec 2 260 mégacycles.

  - Notez que l’activation de l’hyperthreading est recommandée et a été prouvée pour améliorer les performances des serveurs qui prennent en charge l’audio/vidéo.

  - Serveurs Edge : nombre de serveurs Edge requis, basé sur 30% de tous les utilisateurs simultanés communiquant via les serveurs Edge. Ce pourcentage ne peut pas être modifié dans la calculatrice.

  - Magasin d’archivage/d’appel des détails d’enregistrement/de qualité de l’expérience : nombre de magasins requis pour les fonctionnalités d’archivage ou de surveillance, s’ils sont activés dans votre organisation.

  - Serveur de base de données principal requis (pools requis) : nombre de serveurs de base de données principaux requis pour prendre en charge la charge de travail sélectionnée.

En outre, dans la ligne en regard de serveurs frontaux totaux, des informations supplémentaires sont fournies sur la charge de vos serveurs et de votre réseau pour toutes les charges de travail associées.

  - Charge moyenne de l’UC : utilisation moyenne du processeur par serveur frontal.

  - Réseau en Mbits/s : allocation de bande passante requise pour prendre en charge le modèle d’utilisation que vous avez entré.

  - Mémoire en Go : mémoire, en gigaoctets, requise pour chaque serveur frontal.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Ajustement pour vos processeurs

Tous les chiffres d’utilisation du processeur de la feuille de calcul partent du principe que chaque serveur est doté d’un double processeur, d’un cœur avec 2,26 GHz, d’au moins 32 Go de mémoire et de 8 disques durs 10 000-RPM avec au moins 72 Go d’espace disque disponible.

Si vos serveurs ont des processeurs différents, vous pouvez ajuster les chiffres pour qu’ils correspondent à votre matériel.

</div>

</div>

<span> </span>

</div>

</div>

</div>

