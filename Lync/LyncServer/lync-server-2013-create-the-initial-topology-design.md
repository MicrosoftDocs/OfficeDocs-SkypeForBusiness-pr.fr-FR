---
title: 'Lync Server 2013 : création de la conception de topologie initiale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6e679b909fbc6b539e173e98f033a771929893c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Création de la conception de topologie initiale pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Une fois que vous avez terminé l’installation de l’outil de planification Lync Server 2013, vous êtes prêt à démarrer l’outil de planification et à commencer à concevoir l’infrastructure Lync Server 2013 proposée.

<div>


> [!NOTE]  
> L’outil de planification est un outil piloté par un Assistant, avec des guides détaillés pour vous informer de votre processus de prise de décision lors de la conception de vos sites et de votre topologie. Cette rubrique n’est pas un guide exhaustif, mais pour vous aider à commencer à utiliser l’outil de planification dans vos sessions de conception.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Pour commencer à utiliser l’Outil de planification et à créer la conception initiale

1.  Démarrez l’outil de planification Lync Server 2013: cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013**, puis sur **Outil de planification**.

2.  Une fois que l’outil de planification a démarré, la page **Bienvenue dans l’outil de planification pour Microsoft Lync Server 2013** s’affiche. Choisissez l’une des options suivantes pour commencer votre conception :
    
      - **Option 1 : prise en main**   le fait de cliquer sur **commencer** fournit une série spécifique de questions d’entretien avec des sélections appropriées pour définir les critères. Lorsque vous en avez terminé avec la section **Démarrage** initiale, poursuivez avec **Concevoir des sites** pour définir l’architecture de votre site. Pour achever cette option, passez à l’étape 3.
    
      - **Option 2 : conception de sites**   le fait de cliquer sur **concevoir des sites** sur la page d’accueil ignore les questions présentées dans la section prise en **main** . Les informations qui auraient été collectées en répondant aux questions de l’entretien dans la section **prise en main** sont définies sur les valeurs par défaut avec cette option. En cliquant sur **concevoir des sites**, le concepteur expérimenté peut contourner l’entretien initial et modifier les valeurs par défaut, selon vos besoins, sur la page de démarrage des **sites centraux** . Pour achever cette option, ignorez les étapes 3 à 5 et passez directement à l’étape 6.
    
      - **Option 3 : afficher votre topologie**   enregistrée si vous avez déjà terminé et enregistré une topologie à l’aide de l’outil de planification précédemment, vous pouvez ignorer la plupart de ces étapes et commencer par ouvrir et afficher la topologie. Vous pouvez également effectuer des modifications et des mises à jour de la topologie, la réenregistrer, puis l’exporter vers Microsoft Excel ou Microsoft Visio. Pour achever cette option, ignorez les étapes 3 à 12 et passez directement à l’étape 13.

3.  Cliquez sur **prise en main** pour commencer à concevoir votre topologie Lync Server 2013.

4.  Répondez à chaque rubrique en sélectionnant les critères appropriés pour votre conception, puis cliquez sur **Suivant** pour passer à la page suivante de l’Assistant. Cliquez sur **précédent** pour modifier les pages précédentes.
    
    <div>
    

    > [!TIP]  
    > Chaque page contient une description des critères de sélection et des recommandations basées sur les pratiques préférées et la planification de la capacité. Si vous avez besoin de détails supplémentaires, cliquez sur <STRONG>en savoir plus</STRONG> pour consulter des informations détaillées dans la documentation de planification de Lync Server 2013 sur le site Web Microsoft TechNet. Vous devez disposer d’une connexion à Internet pour accéder au site Web Microsoft TechNet.

    
    </div>

5.  Sélectionnez les options appropriées pour votre conception. Une fois les critères initiaux définis, une page viendra confirmer que votre vue d’ensemble des fonctionnalités est complète.

6.  Cliquez sur **concevoir des sites** pour définir votre site central.
    
    <div>
    

    > [!NOTE]  
    > Chaque topologie Lync Server 2013 aura au moins un site central. Votre conception peut avoir un seul site central, un site central avec un certain nombre de sites de succursale, un certain nombre de sites centraux ou un certain nombre de sites centraux avec des sites de succursale associés à chaque site central.

    
    </div>

7.  Dans **nom du site**, tapez le nom qui identifiera ce site central.

8.  Dans **utilisateurs hébergés**sur le site, tapez le nombre d’utilisateurs simultanés locaux attendus qui seront hébergés dans ce site central.

9.  Dans **utilisateurs hébergés**dans le Cloud, tapez le nombre d’utilisateurs simultanés en ligne attendus qui seront hébergés dans ce site central.

10. Modifiez les sélections pour la collaboration en ligne, les utilisateurs, la voix, les options de déploiement supplémentaires ou les applications serveur, selon vos besoins.
    
    <div>
    

    > [!IMPORTANT]  
    > À ce stade de la conception, vous pouvez uniquement sélectionner ou effacer les options de votre déploiement. Toutefois, vous pouvez configurer d’autres options dans une phase ultérieure de l’outil de planification. Certaines options sont également indisponibles et ne peuvent pas être désactivées. En outre, vous pouvez être amené à désactiver une option pour en désactiver une autre. Par exemple, si vous désactivez l’option <STRONG>voix entreprise</STRONG> sous voix, les options <STRONG>Response Group</STRONG>, <STRONG>announcer</STRONG>et <STRONG>parcage d’appel</STRONG> sous applications serveur (toutes les fonctionnalités de voix entreprise) sont également désactivées.

    
    </div>

11. Après avoir défini le nom du site et le nombre d’utilisateurs, cliquez sur **Suivant**.

12. Les pages suivantes demandent des informations sur les domaines SIP, les paramètres de conférence, les paramètres vocaux et l’infrastructure, la messagerie unifiée Exchange, l’accès des utilisateurs externes, les paramètres de conversation permanente, les paramètres du client, les options de colocalisation et les sites de succursale. Répondez à toutes ces questions selon le cas.

13. La dernière question demande si vous souhaitez créer un autre site central. Si vous sélectionnez **Oui**, l’outil de planification revient à la page sites centraux. Si vous sélectionnez **non**, cliquez sur **suivant**, puis sur **dessiner** pour afficher la vue topologique globale de haut niveau.

14. Pour afficher une topologie existante, cliquez sur **Afficher**.

15. Cliquez sur le fichier .xml qui représente la topologie précédemment enregistrée, puis cliquez sur **Ouvrir**.

16. L’outil de planification affiche la page topologie globale. Vous pouvez maintenant commencer à modifier, mettre à jour ou modifier la topologie à l’aide des outils disponibles dans l’outil de planification.

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

