---
title: Création de la conception de topologie initiale pour Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Une fois l’installation de l’outil de planification de Skype entreprise Server terminée, vous pouvez commencer à utiliser l’outil de planification et commencer à concevoir l’infrastructure 2015 de Skype entreprise Server.
ms.openlocfilehash: 47a3725c1307bd6efe57fa07a955004bd6e5ff29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274268"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Création de la conception de topologie initiale pour Skype Entreprise Server 2015

Une fois l’installation de l’outil de planification de Skype entreprise Server terminée, vous pouvez commencer à utiliser l’outil de planification et commencer à concevoir l’infrastructure 2015 de Skype entreprise Server.

> [!NOTE]
>  L’outil de planification est un outil géré par l’Assistant contenant des guides détaillés pour informer votre processus de décision dans la conception de vos sites et de votre topologie. Ce sujet n’est pas une présentation exhaustive, mais simplement pour vous aider à commencer à utiliser l’outil de planification dans vos sessions de conception.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Pour commencer à utiliser l’outil de planification et créer la conception initiale

1. Démarrez l’outil de planification de Skype entreprise Server 2015: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **outil de planification**.

2. Après le démarrage de l’outil de planification, l' **outil Bienvenue dans l’outil de planification de la page 2015 de Skype entreprise Server** s’affiche. Choisissez l’une des options suivantes pour commencer votre conception :

   - **Option 1: commencer** Le fait de cliquer sur mise en **route** fournit une série spécifique de questions relatives aux entretiens et à la définition du critère. Lorsque vous en avez terminé avec la section **Mise en route** initiale, poursuivez avec **Concevoir des sites** pour définir l’architecture de votre site. Pour achever cette option, passez à l’étape 3.

   - **Option 2: créer des sites** Lorsque vous cliquez sur les **sites de création** sur la page d’accueil, les questions posées dans la section mise en **route sont** ignorées. Les informations collectées par les réponses fournies aux questions d’entretien dans la rubrique **Mise en route** sont définies comme valeurs par défaut avec cette option. En cliquant sur **Concevoir des sites**, le concepteur expérimenté peut contourner l’entretien initial et modifier les valeurs par défaut selon ses besoins sur la page de démarrage **Sites centraux**. Pour achever cette option, ignorez les étapes 3 à 5 et passez directement à l’étape 6.

   - **Option 3: afficher la topologie enregistrée** Si vous avez déjà rempli et enregistré une topologie par le biais de l’utilisation précédente de l’outil de planification, vous pouvez ignorer la plupart de ces étapes et commencer par ouvrir et afficher la topologie. Vous pouvez également apporter des modifications et des mises à jour à la topologie, la ré-enregistrer, puis l’exporter dans Microsoft Excel ou Microsoft Visio. Pour achever cette option, ignorez les étapes 3 à 12 et passez directement à l’étape 13.

3. Cliquez sur mise en **route** pour commencer à concevoir votre topologie 2015 de Skype entreprise Server.

4. Répondez à chaque rubrique en sélectionnant les critères appropriés pour votre conception, puis cliquez sur **Suivant** pour passer à la page suivante de l’Assistant. Cliquez sur **Précédent** pour modifier les pages précédentes.

    > [!TIP]
    > Chaque page contient une description des critères de sélection et des recommandations basées sur les pratiques préférées et la planification de la capacité. Si vous avez besoin d’informations supplémentaires, cliquez sur **en savoir plus** pour lire des informations détaillées dans la documentation de planification de Skype entreprise Server 2015 sur le site Web de Microsoft. Vous devez disposer d’une connexion à Internet pour accéder au site Web Microsoft.

5. Sélectionnez les options appropriées pour votre conception. Une fois les critères initiaux définis, une page viendra confirmer que votre vue d’ensemble des fonctionnalités est complète.

6. Cliquez sur **sites de création** pour définir votre site central.

    > [!NOTE]
    > Chaque topologie 2015 de Skype entreprise Server dispose d’au moins un site central. Votre conception est dotée d’un seul site central, d’un site central composé de plusieurs sites de succursales, d’un certain nombre de sites centraux ou d’un certain nombre de sites centraux avec des sites de succursales associés à chaque site central.

7. Dans **nom du site**, tapez le nom qui permettra d’identifier ce site central.

8. Dans la **page utilisateurs hébergés**sur le site, entrez le nombre d’utilisateurs simultanés locaux qui seront hébergés sur ce site central.

9. Dans la **page utilisateurs**dans le Cloud, entrez le nombre prévu d’utilisateurs simultanés en ligne qui seront hébergés sur ce site central.

10. Modifiez les sélections pour Collaboration en ligne, Utilisateurs, Voix, Options de déploiement supplémentaires ou Applications serveur, selon les besoins.

    > [!IMPORTANT]
    > Ce n’est qu’à ce moment de la conception que vous pouvez activer ou désactiver les options de votre déploiement. Toutefois, vous pouvez configurer d’autres options dans une phase ultérieure de l’outil de planification. Certaines options sont également indisponibles et ne peuvent pas être désactivées. En outre, vous pouvez être amené à désactiver une option pour en désactiver une autre. Par exemple, si vous désactivez l’option **Voix Entreprise** sous Voix, les options **Response Group**, **Annonce** et **Parcage d’appel** sous Applications serveur (toutes étant des fonctionnalités de Voix Entreprise) sont également désactivées.

11. Après avoir défini le nom du site et le nombre d’utilisateurs, cliquez sur **Suivant**.

12. Les pages suivantes vous demandent des informations relatives aux domaines SIP, aux paramètres de conférence, aux paramètres vocaux et à l’infrastructure, à la messagerie unifiée, aux options de colocalisation et aux sites de succursales d’Exchange. Répondez à toutes ces questions selon le cas.

13. La question finale vous demande si vous souhaitez créer un autre site central. Si vous sélectionnez **Oui**, l’outil de planification revient à la page sites centraux. Si vous sélectionnez **Non**, cliquez sur **Suivant**, puis sur **Dessiner** pour afficher la vue Topologie globale de niveau supérieur.

14. Pour afficher la topologie existante, cliquez sur **Afficher**.

15. Cliquez sur le fichier .xml qui représente la topologie précédemment enregistrée, puis cliquez sur **Ouvrir**.

16. L’outil de planification affiche la page de topologie globale. Vous pouvez désormais commencer à modifier, à mettre à jour ou à modifier la topologie en utilisant les outils disponibles dans l’outil de planification.

## <a name="see-also"></a>Voir aussi

[Editing the Design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
