---
title: 'Lync Server 2013: création de la conception de topologie initiale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656e9605695fe7dab160469ffa9e9c5075ac807b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Créer la conception de topologie initiale pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Après l’installation de l’outil de planification Lync Server 2013, vous pouvez démarrer l’outil de planification et commencer à concevoir l’infrastructure Lync Server 2013 proposée.

<div>


> [!NOTE]  
> L’outil de planification est un outil géré par l’Assistant contenant des guides détaillés pour informer votre processus de décision dans la conception de vos sites et de votre topologie. Ce sujet n’est pas une présentation exhaustive, mais simplement pour vous aider à commencer à utiliser l’outil de planification dans vos sessions de conception.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Pour commencer à utiliser l’outil de planification et créer la conception initiale

1.  Démarrez l’outil de planification Lync Server 2013: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur outil de **planification**.

2.  Après le démarrage de l’outil de planification, la page **Bienvenue dans l’outil de planification de Microsoft Lync Server 2013** s’affiche. Choisissez l’une des options suivantes pour commencer votre conception :
    
      - **Option 1:**   mise en route cliquez sur mise en **route** fournit une série spécifique de questions d’entretien avec des sélections pertinentes permettant de définir les critères. Lorsque vous en avez terminé avec la section **Mise en route** initiale, poursuivez avec **Concevoir des sites** pour définir l’architecture de votre site. Pour achever cette option, passez à l’étape 3.
    
      - **Option 2: créer des sites**   le fait de cliquer sur **sites de création** dans la page d’accueil ignore les questions présentées dans la section mise en **route** . Les informations collectées par les réponses fournies aux questions d’entretien dans la rubrique **Mise en route** sont définies comme valeurs par défaut avec cette option. En cliquant sur **Concevoir des sites**, le concepteur expérimenté peut contourner l’entretien initial et modifier les valeurs par défaut selon ses besoins sur la page de démarrage **Sites centraux**. Pour achever cette option, ignorez les étapes 3 à 5 et passez directement à l’étape 6.
    
      - **Option 3: afficher votre topologie**   enregistrée si vous avez déjà terminé et enregistré une topologie lors de l’utilisation précédente de l’outil de planification, vous pouvez ignorer la plupart de ces étapes et commencer en ouvrant et en affichant la topologie. Vous pouvez également apporter des modifications et des mises à jour à la topologie, la ré-enregistrer, puis l’exporter dans Microsoft Excel ou Microsoft Visio. Pour achever cette option, ignorez les étapes 3 à 12 et passez directement à l’étape 13.

3.  Cliquez sur mise en **route** pour commencer à concevoir votre topologie Lync Server 2013.

4.  Répondez à chaque rubrique en sélectionnant les critères appropriés pour votre conception, puis cliquez sur **Suivant** pour passer à la page suivante de l’Assistant. Cliquez sur **Précédent** pour modifier les pages précédentes.
    
    <div>
    

    > [!TIP]  
    > Chaque page contient une description des critères de sélection et des recommandations basées sur les pratiques préférées et la planification de la capacité. Si vous avez besoin d’informations supplémentaires, cliquez sur <STRONG>en savoir plus</STRONG> pour lire des informations détaillées dans la documentation de planification de Lync Server 2013 sur le site Web Microsoft TechNet. Vous devez disposer d’une connexion à Internet pour accéder au site web Microsoft TechNet.

    
    </div>

5.  Sélectionnez les options appropriées pour votre conception. Une fois les critères initiaux définis, une page viendra confirmer que votre vue d’ensemble des fonctionnalités est complète.

6.  Cliquez sur **sites de création** pour définir votre site central.
    
    <div>
    

    > [!NOTE]  
    > Chaque topologie Lync Server 2013 dispose d’au moins un site central. Votre conception est dotée d’un seul site central, d’un site central composé de plusieurs sites de succursales, d’un certain nombre de sites centraux ou d’un certain nombre de sites centraux avec des sites de succursales associés à chaque site central.

    
    </div>

7.  Dans **nom du site**, tapez le nom qui permettra d’identifier ce site central.

8.  Dans la **page utilisateurs hébergés**sur le site, entrez le nombre d’utilisateurs simultanés locaux qui seront hébergés sur ce site central.

9.  Dans la **page utilisateurs**dans le Cloud, entrez le nombre prévu d’utilisateurs simultanés en ligne qui seront hébergés sur ce site central.

10. Modifiez les sélections pour Collaboration en ligne, Utilisateurs, Voix, Options de déploiement supplémentaires ou Applications serveur, selon les besoins.
    
    <div>
    

    > [!IMPORTANT]  
    > Ce n’est qu’à ce moment de la conception que vous pouvez activer ou désactiver les options de votre déploiement. Toutefois, vous pouvez configurer d’autres options dans une phase ultérieure de l’outil de planification. Certaines options sont également indisponibles et ne peuvent pas être désactivées. En outre, vous pouvez être amené à désactiver une option pour en désactiver une autre. Par exemple, si vous désactivez l’option <STRONG>Voix Entreprise</STRONG> sous Voix, les options <STRONG>Response Group</STRONG>, <STRONG>Annonce</STRONG> et <STRONG>Parcage d’appel</STRONG> sous Applications serveur (toutes étant des fonctionnalités de Voix Entreprise) sont également désactivées.

    
    </div>

11. Après avoir défini le nom du site et le nombre d’utilisateurs, cliquez sur **Suivant**.

12. Les pages suivantes vous demandent des informations relatives aux domaines SIP, aux paramètres de conférence, aux paramètres vocaux et à l’infrastructure, à la messagerie unifiée, aux options de colocalisation et aux sites de succursales d’Exchange. Répondez à toutes ces questions selon le cas.

13. La question finale vous demande si vous souhaitez créer un autre site central. Si vous sélectionnez **Oui**, l’outil de planification revient à la page sites centraux. Si vous sélectionnez **Non**, cliquez sur **Suivant**, puis sur **Dessiner** pour afficher la vue Topologie globale de niveau supérieur.

14. Pour afficher la topologie existante, cliquez sur **Afficher**.

15. Cliquez sur le fichier .xml qui représente la topologie précédemment enregistrée, puis cliquez sur **Ouvrir**.

16. L’outil de planification affiche la page de topologie globale. Vous pouvez désormais commencer à modifier, à mettre à jour ou à modifier la topologie en utilisant les outils disponibles dans l’outil de planification.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modification de la conception dans Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

