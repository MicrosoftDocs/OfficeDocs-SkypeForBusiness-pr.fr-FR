---
title: Vérifier votre connexion Internet pour le système téléphonique Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Vérifier que votre internet est prêt pour le système téléphonique Teams
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 7cef6f8b9a3bfa6aa99fe342f8d1abf66f7c6594
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480934"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>Vérifier votre connexion Internet pour le système téléphonique Teams

Teams Phone System est la technologie de Microsoft permettant d’activer les fonctionnalités téléphoniques dans Microsoft Teams à l’aide du cloud Microsoft 365. Chaque appareil qui utilise Microsoft Teams et le système téléphonique a besoin d’une connexion à Internet.

Pour bénéficier de la meilleure expérience de système téléphonique, vous avez besoin d’une connexion Internet haut débit qui peut prendre en charge le nombre maximal d’appels téléphoniques que votre organisation peut effectuer à tout moment. Vous devez également vous assurer que les ordinateurs de votre réseau peuvent atteindre les services Microsoft 365.

## <a name="check-your-internet-connection-speed"></a>Vérifier la vitesse de votre connexion Internet

Cet article vous aide à déterminer si votre connexion Internet est suffisamment rapide pour le nombre de personnes qui doivent passer des appels téléphoniques. Vous fournirez des informations sur votre organisation et récupérerez un rapport qui indique la quantité de votre connexion Internet utilisée par Teams et le système téléphonique.

### <a name="gather-information-about-your-internet-connection-and-users"></a>Collecter des informations sur votre connexion Internet et vos utilisateurs

Avant de commencer, vous avez besoin des informations suivantes :

* La vitesse de votre connexion Internet
* Combien de personnes utiliseront le système téléphonique principalement à partir de votre bureau
* Combien de personnes utiliseront le système téléphonique principalement à partir d’un emplacement distant, tel qu’un bureau à domicile

### <a name="enter-your-information-into-the-network-planner"></a>Entrer vos informations dans le Planificateur de réseau

Procédez comme suit :

1. Dans un navigateur, allez à [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com). Connectez-vous à l’aide d’un compte disposant des autorisations d’administrateur général. Le compte que vous avez utilisé pour vous inscrire à Microsoft 365 dispose de ces autorisations.
2. Ouvrez **Planification**, puis sélectionnez **Planificateur de réseau**.
3. Sous **Plans réseau**, sélectionnez **Ajouter**. Entrez un nom à votre plan, puis sélectionnez **Appliquer**.
4. Sélectionnez le nom de votre plan de réseau.
5. Sur la page suivante, sélectionnez **Ajouter un site réseau** dans l’onglet **Sites réseau**.
6. Renseignez le **nom du site réseau**, **les utilisateurs réseau** et les champs **de capacité de liaison Internet** , puis **sélectionnez Enregistrer**. Laissez les autres champs vides dans cet écran, et ne sélectionnez pas les options **ExpressRoute** ou **connecté au réseau étendu**.
7. Dans l’onglet **Rapport**, sélectionnez **Démarrer un rapport**.
8. Entrez un **nom de rapport** et le nombre **d’utilisateurs réseau** (**Office** et **Distant**), puis **sélectionnez Générer un rapport** pour créer un rapport qui affiche les exigences de bande passante pour Teams. Nous vous indiquerons comment lire le rapport dans la section suivante.

### <a name="find-your-minimum-internet-connection-speed"></a>Rechercher votre vitesse de connexion Internet minimale

Lorsque vous sélectionnez **Générer un rapport**, Microsoft 365 crée un rapport.

Sous la colonne **Impact** et dans la ligne **Office 365**, ce numéro indique la quantité de votre connexion Internet que Teams et le système téléphonique utiliseront. Nous vous recommandons de ne pas dépasser 30 % de la vitesse totale de connexion Internet. Par exemple, si votre connexion Internet est *de 60 Mbits/s*, Teams et le système téléphonique ne doivent pas utiliser plus de *18 Mbits/s*.

Utilisez cette équation pour déterminer votre vitesse de connexion Internet minimale : <*numéro d’impact> /0,3*.  

Supposons que le nombre d’impact est *de 4 6875 Mbits/s*. Le calcul pour trouver votre vitesse de connexion Internet minimale serait *4,6875 / 0,3 = 15,6*. Dans ce cas, la vitesse de connexion Internet doit être d’au moins *15,6 Mbits/s*.

Si Teams et le système téléphonique utilisent plus de 30 % de la vitesse totale de votre connexion Internet, le numéro **Impact** apparaîtra en rouge. Dans ce cas, vous devrez peut-être mettre à niveau votre connexion Internet.

![Avertissement de vitesse de connexion.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> L’impact sur la bande passante fourni par le Planificateur de réseau est une estimation uniquement. Il est recommandé d’utiliser le [tableau de bord qualité](../cqd-what-is-call-quality-dashboard.md) des appels pour surveiller de manière pro-active l’expérience utilisateur pour les appels audio et vidéo avec Microsoft Teams au sein de votre organisation.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>S’assurer que les ordinateurs et les appareils de votre réseau peuvent accéder à Microsoft 365

Les ordinateurs et appareils qui utilisent le système téléphonique doivent utiliser des ports réseau spécifiques pour communiquer avec les services Microsoft 365. Ces ports sont essentiellement des portes par lesquelles les appareils communiquent entre eux via un réseau ou Internet. Votre pare-feu doit autoriser les appareils de votre réseau à accéder à Microsoft 365 sur les ports réseau *sortants* suivants :

* **Ports TCP** 80 et 443
* **Ports UDP** 3478, 3479, 3480 et 3481

Le moyen le plus simple de vérifier si votre pare-feu autorise la communication sur ces ports réseau consiste à effectuer un test de connectivité à l’aide de [l’outil de connectivité réseau Microsoft 365](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) à partir de l’emplacement du bureau que vous souhaitez tester. Une fois le test terminé, vérifiez les résultats et les recommandations.
