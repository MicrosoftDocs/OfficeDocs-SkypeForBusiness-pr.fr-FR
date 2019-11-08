---
title: Vérifiez votre connexion Internet
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4dbfd1bdaec48ebe8c6adbed86da431a6f4ecbfc
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972275"
---
# <a name="check-your-internet-connection"></a>Vérifiez votre connexion Internet

Business Voice réside dans le cloud avec Microsoft 365. Tous les ordinateurs et appareils utilisant Microsoft Teams et Business Voice ont besoin d’une connexion Internet. Pour tirer le meilleur parti de Business Voice, une connexion Internet haut débit capable de prendre en charge le nombre d’appels téléphoniques attendu à tout moment est recommandée. Vous devez également vous assurer que les ordinateurs de votre réseau peuvent accéder aux serveurs Microsoft 365.

Pour appliquer cette procédure, vous devez disposer d’un client avec l’un des abonnements suivants :

* Office 365 Business Essentials
* Office 365 Business Premium
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 Business

Vous n’avez pas besoin d’une licence Business Voice pour suivre cette procédure.

## <a name="check-your-internet-connection-speed"></a>Vérifier la vitesse de votre connexion Internet

Cet article vous aide à déterminer si votre connexion Internet est suffisamment rapide pour le nombre de personnes qui ont à effectuer des appels téléphoniques, à héberger des vidéoconférences, etc. Vous allez fournir des informations sur votre organisation et obtenir un rapport indiquant dans quelle mesure votre connexion Internet sera utilisée par Teams et Business Voice.

### <a name="get-information-about-your-internet-connection-and-users"></a>Obtenir des informations sur votre connexion Internet et vos utilisateurs

Avant de commencer, vous devez disposer des informations suivantes :

* La vitesse de votre connexion Internet.
* Le nombre de personnes qui utiliseront Business Voice principalement à partir de vos bureaux.
* Le nombre de personnes qui utiliseront Business Voice principalement à partir d’un emplacement distant, par exemple en télétravail.

### <a name="enter-your-information-into-the-network-planner"></a>Entrer vos informations dans le Planificateur de réseau

Procédez comme suit :

1. Ouvrez un navigateur, accédez à https://admin.teams.microsoft.com et connectez-vous à l’aide d’un compte disposant des autorisations d’administrateur général. Le compte que vous avez utilisé pour vous inscrire à Office 365 dispose de ces autorisations.
1. Ouvrez **Paramètres à l’échelle de l’organisation**, puis sélectionnez **Planificateur de réseau**.
1. Sous **Plans réseau**, sélectionnez **Ajouter**. Donnez un nom à votre plan, puis sélectionnez **Appliquer**. Votre plan réseau doit se présenter comme suit :

    ![Écran principal du Planificateur de réseau](../media/network-planner-main.png)
1. Cliquez sur le nom de votre plan réseau (**Bureau principal** dans l’image ci-dessus).
1. Sur la page suivante, sélectionnez **Ajouter un site réseau** dans l’onglet **Sites réseau**.
1. Renseignez les informations suivantes, puis sélectionnez **Enregistrer**.

    ![Informations sur le site du Planificateur de réseau](../media/network-planner-site-info.png)
1. Dans l’onglet **Rapport**, sélectionnez **Démarrer un rapport**.
1. Renseignez les informations suivantes, puis sélectionnez **Générer un rapport**.

    ![Informations sur le rapport du Planificateur de réseau](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>Identifier votre vitesse de connexion Internet minimale

Lorsque vous sélectionnez **Générer un rapport**, Office 365 crée un rapport semblable à ce qui suit :

![Détails du rapport du Planificateur de réseau](../media/network-planner-report.png)

Le chiffre mis en surbrillance indique la part de votre connexion Internet utilisée par Teams et Business Voice. Nous vous recommandons de faire en sorte que ce chiffre ne dépasse pas 30 % de la vitesse totale de votre connexion Internet. Par exemple, si votre connexion Internet est de 60 Mbits/s, Teams et Business Voice ne doivent pas utiliser plus de 18 Mbits/s.

Vous pouvez déterminer votre vitesse de connexion Internet minimale grâce au calcul suivant : `<highlighted number> / .3`. Avec le chiffre mis en surbrillance dans l’image ci-dessus, le calcul est `4.6875 / .3 = 15.6`. Cela signifie que votre vitesse de connexion Internet minimale doit être 15,6 Mbits/s.

Si Teams et Business Voice utilisent plus de 30 % de la vitesse de connexion Internet totale, le chiffre mis en surbrillance s’affiche en rouge. Dans ce cas, vous devrez peut-être mettre à niveau votre connexion Internet.

![Avertissement de vitesse de connexion](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>S’assurer que les ordinateurs et les appareils de votre réseau peuvent accéder à Microsoft 365

Pour fonctionner correctement, les ordinateurs et les appareils que vous voulez utiliser avec Business Voice doivent communiquer avec les serveurs Microsoft 365 via des ports réseau spécifiques. Les ports réseau fonctionnent comme des portes via lesquelles les ordinateurs et les appareils peuvent communiquer entre eux sur un réseau ou sur Internet. Votre pare-feu doit autoriser les ordinateurs et les appareils de votre réseau à accéder à Microsoft 365 sur les ports réseau sortants suivants :

* **Ports TCP** 80 et 443
* **Ports UDP** 3478, 3479, 3480 et 3481

Le moyen le plus simple de vérifier si votre pare-feu autorise la communication sur ces ports réseau consiste à effectuer un appel de test à l’aide de Teams. Pour passer un appel de test, procédez comme suit :

1. Accédez à https://aka.ms/getteams sur un ordinateur de votre réseau pour installer Teams. Vérifiez que des haut-parleurs et un microphone sont connectés à cet ordinateur.
2. Ouvrez Teams et connectez-vous à l’aide d’un compte Microsoft 365.
3. Dans Teams, sélectionnez votre image de profil, puis **Paramètres** > **Périphériques**.
4. Sélectionnez **Passer un appel de test** sous **Périphériques audio**.
5. Suivez les invites pour laisser un message et l’écouter ensuite.

* Si l’appel aboutit et que vous entendez votre message, votre pare-feu est correctement configuré.
* Si l’appel aboutit mais que vous ne parvenez pas à entendre les invites ou votre message, assurez-vous que vos haut-parleurs et votre microphone sont correctement configurés et détectés par l’ordinateur. Réessayez.
* Si l’appel n’aboutit pas, ou s’il aboutit mais que vous ne pouvez pas écouter votre message, vous devrez peut-être mettre à jour votre pare-feu afin d’autoriser les ports réseau répertoriés ci-dessus. Consultez la documentation de votre pare-feu pour savoir comment autoriser les ports réseau à accéder à Internet, ou contactez un spécialiste informatique pour vous aider.

Si vous êtes un professionnel de l’informatique et que vous avez besoin d’informations supplémentaires sur la préparation de réseaux plus vastes ou plus complexes afin de prendre en charge Business Voice, consultez l’article [Évaluer mon environnement](../3-envision-evaluate-my-environment.md). L’article [Évaluer mon environnement](../3-envision-evaluate-my-environment.md) fournit des informations complémentaires sur les exigences en matière de bande passante, de proxy et de pare-feu, ainsi que sur le test de votre réseau à l’aide de l’[Outil d’évaluation du réseau](../3-envision-evaluate-my-environment.md#test-the-network).
