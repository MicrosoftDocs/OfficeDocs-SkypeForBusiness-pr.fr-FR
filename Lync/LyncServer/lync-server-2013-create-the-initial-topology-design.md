---
title: 'Lync Server 2013 : Création de la conception de topologie initiale'
TOCTitle: Création de la conception de topologie initiale
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615047(v=OCS.15)
ms:contentKeyID: 53095564
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création de la conception de topologie initiale pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Une fois l’installation de l’outil de planification Lync Server 2013 terminée, vous êtes prêt à démarrer l’outil de planification et à commencer la conception de l’infrastructure Lync Server 2013 proposée.

> [!NOTE]  
> L’outil de planification est un outil muni d’un assistant qui vous guide dans votre processus décisionnel de conception de vos sites et de votre topologie. Cette rubrique n’est conçue comme un guide exhaustif, mais pour vous aider à démarrer dans l’utilisation de l’outil de planification dans vos sessions de conception.

## Pour commencer à utiliser l’Outil de planification et à créer la conception initiale

1.  Démarrez l’outil de planification Lync Server 2013: cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Outil de planification**.

2.  Une fois l’outil de planification démarré, la page **Outil de planification pour Microsoft Lync Server 2010** s’ouvre. Choisissez une des options suivantes pour commencer votre conception :
    
      - **Option 1 : démarrer**   Si vous cliquez sur **Démarrer** , une série de questions spécifiques s’affiche avec des sélections pertinentes pour définir les critères. Lorsque vous en avez terminé avec la section **Démarrage** initiale, poursuivez avec **Concevoir des sites** pour définir l’architecture de votre site. Pour achever cette option, passez à l’étape 3.
    
      - **Option 2 : concevoir des sites**   Si vous cliquez sur **Concevoir des sites** dans la page d’accueil, cela permet de contourner les questions d’entretien présentées dans la section **Démarrer** . Les informations collectées par les réponses fournies aux questions d’entretien dans la rubrique **Démarrer** sont définies comme valeurs par défaut avec cette option. En cliquant sur **Concevoir des sites** , le concepteur expérimenté peut contourner l’entretien initial et modifier les valeurs par défaut selon ses besoins sur la page de démarrage **Sites centraux** . Pour achever cette option, ignorez les étapes 3 à 5 et passez directement à l’étape 6.
    
      - **Option 3 : afficher votre topologie enregistrée**   Si vous avez déjà créé et enregistré une topologie lors d’une précédente utilisation de l’outil de planification, vous pouvez ignorer la plupart de ces étapes et commencer directement par l’ouverture et l’affichage de la topologie. Vous pouvez également apporter des modifications et des mises à jour à la topologie, la ré-enregistrer, puis l’exporter dans Microsoft Excel ou Microsoft Visio. Pour achever cette option, ignorez les étapes 3 à 12 et passez directement à l’étape 13.

3.  Cliquez sur **Démarrer** pour commencer à concevoir votre topologie Lync Server 2013.

4.  Répondez à chaque rubrique en sélectionnant les critères appropriés pour votre conception, puis cliquez sur **Suivant** pour passer à la page suivante de l’Assistant. Cliquez sur **Précédent** pour modifier les pages précédentes.
    
    > [!TIP]  
    > Chaque page contient une description des critères de sélection et des recommandations basées sur les pratiques préférées et la planification de la capacité. Si vous avez besoin d’informations supplémentaires, cliquez sur <strong>En savoir plus</strong> pour lire des informations détaillées dans la documentation de planification de Lync Server 2013 sur le site web Microsoft TechNet. Vous devez disposer d’une connexion à Internet pour accéder au site web Microsoft TechNet.

5.  Sélectionnez les options appropriées pour votre conception. Une fois les critères initiaux définis, une page viendra confirmer que votre vue d’ensemble des fonctionnalités est complète.

6.  Cliquez sur **Concevoir des sites** pour définir votre site central.
    
    > [!NOTE]  
    > Chaque topologie Lync Server 2013 aura au moins un site central. Votre conception peut comprendre un seul site central, un site central avec un certain nombre de sites de succursale, un certain nombre de sites centraux, ou un certain nombre de sites centraux avec des sites de succursale associés à chaque site central.

7.  Dans **Nom du site** , tapez le nom qui identifiera ce site central.

8.  Dans **Utilisateurs hébergés sur le site** , tapez le nombre d’utilisateurs concurrents locaux attendus qui seront hébergés dans ce site central.

9.  Dans **Utilisateurs hébergés dans le nuage** , tapez le nom d’utilisateurs en ligne concurrents qui seront hébergés dans ce site central.

10. Modifiez les sélections pour Collaboration en ligne, Utilisateurs, Voix, Options de déploiement supplémentaires ou Applications serveur, selon les besoins.
    
    > [!IMPORTANT]  
    > Ce n’est qu’à ce moment de la conception que vous pouvez activer ou désactiver les options de votre déploiement. Cependant, vous pourrez configurer d’autres options lors d’une phase ultérieure de l’outil de planification. Certaines options sont également indisponibles et ne peuvent pas être désactivées. En outre, vous pouvez être amené à désactiver une option pour en désactiver une autre. Par exemple, si vous désactivez l’option <strong>Voix Entreprise</strong> sous Voix, les options <strong>Response Group</strong> , <strong>Annonce</strong> et <strong>Parcage d’appel</strong> sous Applications serveur (toutes étant des fonctionnalités de Voix Entreprise) sont également désactivées.

11. Après avoir défini le nom du site et le nombre d’utilisateurs, cliquez sur **Suivant** .

12. Les pages suivantes demandent des informations sur les domaines SIP, les paramètres de conférence, les paramètres et l’infrastructure des fonctions vocales, la messagerie unifiée Exchange, l’accès des utilisateurs externes, les paramètres conversation permanente, les paramètres client, les options de colocalisation et les sites de succursale. Répondez à toutes ces questions selon le cas.

13. La dernière question vous demande si vous souhaitez créer un autre site central. Si vous sélectionnez **Oui** , l’outil de planification revient à la page Sites centraux. Si vous sélectionnez **Non** , cliquez sur **Suivant** , puis sur **Dessiner** pour afficher la vue Topologie globale de niveau supérieur.

14. Pour afficher la topologie existante, cliquez sur **Afficher** .

15. Cliquez sur le fichier .xml qui représente la topologie précédemment enregistrée, puis cliquez sur **Ouvrir** .

16. L’outil de planification affiche la page Topologie globale. Vous pouvez commencer à modifier, mettre à jour ou modifier la topologie à l’aide des outils disponibles dans l’outil de planification.

## Voir aussi

#### Concepts

[Modification de la conception dans Lync Server 2013](lync-server-2013-editing-the-design.md)

