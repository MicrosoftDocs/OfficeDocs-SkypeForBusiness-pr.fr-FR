---
title: Création de la conception de topologie initiale pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Lorsque vous avez terminé l’installation de la Skype pour outil de planification de serveur Business, vous êtes prêt à démarrer l’outil de planification et de commencer à concevoir le Skype proposé pour l’infrastructure de Business Server 2015.
ms.openlocfilehash: 9925ad9e4294ef2a1e4b90f6e1de9780bbb83260
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Création de la conception de topologie initiale pour Skype Entreprise Server 2015
 
Lorsque vous avez terminé l’installation de la Skype pour outil de planification de serveur Business, vous êtes prêt à démarrer l’outil de planification et de commencer à concevoir le Skype proposé pour l’infrastructure de Business Server 2015.
  
> [!NOTE]
>  L’outil de planification est un outil de pilotée par Assistant avec des guides détaillés pour informer votre processus décisionnel dans la conception de vos sites et la topologie. Cette rubrique est destinée à pas comme un guide exhaustif, mais simplement pour vous aider à démarrer à l’aide de l’outil de planification de vos sessions de conception.
  
### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Mise en route à l’aide de l’outil de planification et de créer la conception initiale

1. Démarrer le Skype pour outil de planification Microsoft Business Server 2015 : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Outil de planification**.
    
2. Après le démarrage de l’outil de planification, la page **Bienvenue dans l’outil de planification pour Skype pour Business Server 2015** s’affiche. Choisissez l’une des options suivantes pour commencer votre conception :
    
   - **Option 1 : mise en route** Cliquez sur **Mise en route** fournit une série spécifique de questions d’entretien avec les sélections appropriées pour définir les critères. Lorsque vous en avez terminé avec la section **Mise en route** initiale, poursuivez avec **Concevoir des sites** pour définir l’architecture de votre site. Pour achever cette option, passez à l’étape 3.
    
   - **Option 2 : conception des Sites** En cliquant sur les **Sites de la conception** à la page d’accueil permet d’éviter aux questions présentées dans la section **Mise en route** . Les informations collectées par les réponses fournies aux questions d’entretien dans la rubrique **Mise en route** sont définies comme valeurs par défaut avec cette option. En cliquant sur **Concevoir des sites**, le concepteur expérimenté peut contourner l’entretien initial et modifier les valeurs par défaut selon ses besoins sur la page de démarrage **Sites centraux**. Pour achever cette option, ignorez les étapes 3 à 5 et passez directement à l’étape 6.
    
   - **Option 3 : afficher votre topologie enregistrée** Si vous avez déjà terminé et enregistré une topologie grâce à l’utilisation précédente de l’outil de planification, vous pouvez ignorer la plupart de ces étapes et démarrer à l’ouverture et l’affichage de la topologie. Vous pouvez également apporter des modifications et des mises à jour à la topologie, la ré-enregistrer, puis l’exporter dans Microsoft Excel ou Microsoft Visio. Pour achever cette option, ignorez les étapes 3 à 12 et passez directement à l’étape 13.
    
3. Cliquez sur **Démarrer** pour commencer à concevoir votre Skype pour la topologie de Business Server 2015.
    
4. Répondez à chaque rubrique en sélectionnant les critères appropriés pour votre conception, puis cliquez sur **Suivant** pour passer à la page suivante de l’Assistant. Cliquez sur **Précédent** pour modifier les pages précédentes.
    
    > [!TIP]
    > Chaque page contient une description des critères de sélection et des recommandations basées sur les pratiques préférées et la planification de la capacité. Si vous avez besoin d’informations supplémentaires, cliquez sur **en savoir plus** pour obtenir des informations détaillées à partir de la Skype pour la planification de Business Server 2015 de documentation sur le site Web TechNet de Microsoft. Vous devez disposer d’une connexion à Internet pour accéder au site web Microsoft TechNet.
  
5. Sélectionnez les options appropriées pour votre conception. Une fois les critères initiaux définis, une page viendra confirmer que votre vue d’ensemble des fonctionnalités est complète. 
    
6. Cliquez sur **Sites de conception** pour définir votre site central.
    
    > [!NOTE]
    > Chaque Skype pour Business Server 2015 topologie aura au moins un site central. Votre conception peut avoir un seul site central, un site central avec un nombre de sites de la succursale, un certain nombre de sites centraux ou un nombre de sites centraux avec un site de succursale associé à chaque site central. 
  
7. Dans la zone **Nom du Site**, tapez le nom qui identifiera ce site central.
    
8. **Les utilisateurs du Site hébergé**, tapez le nombre prévu d’utilisateurs simultanés sur site seront hébergés dans ce site central.
    
9. **Les utilisateurs d’hébergement Cloud**, tapez le nombre prévu d’utilisateurs simultanés en ligne, qui seront hébergés dans ce site central.
    
10. Modifiez les sélections pour Collaboration en ligne, Utilisateurs, Voix, Options de déploiement supplémentaires ou Applications serveur, selon les besoins.
    
    > [!IMPORTANT]
    > Ce n’est qu’à ce moment de la conception que vous pouvez activer ou désactiver les options de votre déploiement. Toutefois, vous pouvez configurer plusieurs options dans une phase ultérieure de l’outil de planification. Certaines options sont également indisponibles et ne peuvent pas être désactivées. En outre, vous pouvez être amené à désactiver une option pour en désactiver une autre. Par exemple, si vous désactivez l’option **Voix Entreprise** sous Voix, les options **Response Group**, **Annonce** et **Parcage d’appel** sous Applications serveur (toutes étant des fonctionnalités de Voix Entreprise) sont également désactivées.
  
11. Après avoir défini le nom du site et le nombre d’utilisateurs, cliquez sur **Suivant**.
    
12. Les pages suivantes demanderont des informations à propos de SIP domaines, paramètres de conférence, paramètres de la voix et l’infrastructure, messagerie unifiée Exchange, l’accès des utilisateurs externes, Chat persistant paramètres, paramètres du client, possibilités de colocalisation et sites des succursales. Répondez à toutes ces questions selon le cas.
    
13. La question finale vous demande si vous souhaitez créer un autre site central. Si vous sélectionnez **Oui**, l’outil de planification retourne à la page Sites centraux. Si vous sélectionnez **Non**, cliquez sur **Suivant**, puis sur **Dessiner** pour afficher la vue Topologie globale de niveau supérieur.
    
14. Pour afficher la topologie existante, cliquez sur **Afficher**.
    
15. Cliquez sur le fichier .xml qui représente la topologie précédemment enregistrée, puis cliquez sur **Ouvrir**.
    
16. L’outil de planification affiche la page de la topologie globale. Vous pouvez maintenant commencer la modification, la mise à jour ou la modification de la topologie en utilisant les outils disponibles dans l’outil de planification.
    
## <a name="see-also"></a>Voir aussi

#### 

[Modification de la conception](http://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)

