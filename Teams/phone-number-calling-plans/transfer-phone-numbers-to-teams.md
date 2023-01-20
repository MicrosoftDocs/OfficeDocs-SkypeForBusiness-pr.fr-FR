---
title: Transférer des numéros de téléphone vers Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment utiliser l’Assistant Portage pour transférer votre numéro de téléphone de votre fournisseur de services actuel vers Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dd296bcf987016cf77af538edcb2e04328ab525b
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835477"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Transférer des numéros de téléphone vers Microsoft Teams

Utilisez l’Assistant Portage dans le Centre d’administration Microsoft Teams pour transférer vos numéros de téléphone de votre fournisseur de services actuel vers Teams. Une fois que vous avez transféré vos numéros de téléphone vers Teams, Microsoft devient votre fournisseur de services et vous facture ces numéros de téléphone.

Avant de commencer, nous vous recommandons de consulter les informations contenues dans [Qu’est-ce qu’une commande de transfert ?](port-order-overview.md) Si vous avez des numéros de service pour les ponts de conférence rendez-vous, des standards automatiques ou d’autres numéros de service, des numéros de téléphone gratuits, ou si vous avez plus de 999 numéros de téléphone d’utilisateur (abonnés) que vous devez transférer vers Teams, consultez [Gérer les numéros de téléphone pour votre organisation afin](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) de télécharger les formulaires appropriés et de nous les envoyer.

  > [!NOTE]
  > Nous traitons les commandes de transfert de numéros de téléphone uniquement États-Unis jours ouvrables et non les jours fériés ou les week-ends.
  >
  > La disponibilité du portage pour les numéros de téléphone gratuits peut varier selon le pays et la région. Pour en savoir plus, reportez-vous aux documents spécifiques à votre pays ou région pour voir la prise en charge disponible pour le service de portage.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Créer une commande de transfert et transférer vos numéros de téléphone vers Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Numéros de téléphone vocaux** > . Sélectionnez **Nombres**, puis **Port** pour démarrer l’Assistant Portage.
2. Passez en revue les informations de la page **Prise en main** , puis, lorsque vous êtes prêt, sélectionnez **Suivant**.
3. Dans la page **Sélectionner l’emplacement et le type de numéro** , spécifiez les éléments suivants, puis sélectionnez **Suivant** :

    - **Pays ou région** : pays ou région où vous obtenez des numéros.
    - **Type de numéro de téléphone** : type de numéro, tel que les numéros géographiques ou gratuits.
    - **Nombres affectés à** : à quoi les numéros sont attribués. Par exemple, les utilisateurs ou les fonctionnalités vocales ou de conférence.

4. Dans la page **Ajouter des informations** sur le compte, effectuez les étapes suivantes, puis sélectionnez **Suivant**.

    > [!IMPORTANT]
    > Les informations affichées sur cette page sont déterminées par le pays ou la région et le type de numéro. Chaque pays et région a des réglementations différentes sur les informations requises pour les numéros de port. Ce que vous voyez sur cette page peut être différent de ce qui est décrit ici.

    - **Détails de la commande** : 
        - **Nom de la commande** : nom de votre commande
        - **E-mails de notification** : Email adresses pour recevoir des notifications de commande. Si vous entrez plusieurs adresses e-mail, séparez-les par un point-virgule.
        - **Date de transfert** : date de transfert émise par votre fournisseur de services actuel.
    - **Détails du numéro de téléphone**
        - **Type** de port : que vous effectuiez un port complet pour transférer tous vos numéros ou un port partiel pour transférer certains de vos numéros.
    - **Personne demandant des détails**  
        - Nom de votre organisation et coordonnées de la personne qui demande le transfert.
    - **Détails du fournisseur actuel**
        - **Numéro de téléphone de facturation (BTN)** : votre NUMÉRO BTN au format E.164, qui nécessite un signe + pour ajouter le numéro. Par exemple, pour un nombre Amérique du Nord, utilisez le format +1XXXYYYZZZZZZ.
        - Autres détails, notamment le nom de votre fournisseur de services actuel, votre numéro de compte et votre adresse de service.
            
5. Dans la page **Ajouter des numéros** , sélectionnez **Sélectionner un fichier**, recherchez et sélectionnez le fichier CSV qui contient les numéros de téléphone que vous souhaitez transférer, puis sélectionnez **Suivant**.  

    > [!NOTE]
    > Le fichier CSV ne doit avoir qu’une seule colonne avec un en-tête nommé **PhoneNumber**. Chaque numéro de téléphone doit se trouver sur une ligne distincte et peut être des chiffres uniquement ou au format E.164.

6. Dans la page **Terminer votre commande** , sélectionnez **Charger une lettre d’autorisation signée** pour charger une copie numérisée de la lettre d’autorisation signée.

    Si vous n’avez pas encore téléchargé et signé le LOA, procédez comme suit :
    
    1. Sélectionnez **Télécharger le modèle** pour télécharger le LOA pour votre pays ou région. 
    2. Imprimez le LOA.
    3. Faites signer le LOA par la personne autorisée à apporter des modifications au compte.
    4. Analysez le LOA signé, puis sélectionnez **Charger une lettre d’autorisation signée** pour la charger.

    > [!NOTE]
    > Après avoir chargé votre LOA, envoyez votre commande. Le simple chargement du LOA ne suffit pas. Vous devez également envoyer la commande pour qu’elle soit traitée.
    >
    > Pour plus d’informations sur les contrats d’accès pour le port/le transfert de numéros de téléphone existants et les exigences de documentation supplémentaires, consultez [Gérer les numéros de téléphone pour le forfait d’appels](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).
    >
    > Pour porter/transférer plus de 999 numéros de téléphone ou si vous rencontrez des problèmes avec le processus de portage dans le centre d’administration Microsoft Teams, vous pouvez [envoyer manuellement une commande de transfert](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) au Service Desk TNS pour votre région.

7. Passez en revue les détails de votre commande, puis sélectionnez **Envoyer**.

## <a name="what-happens-next"></a>Que va-t-il se passer ensuite ?

Lorsque nous recevons votre commande de transfert, vous recevez un e-mail qui vérifie votre demande. Votre demande est vérifiée et mise à jour quotidiennement, et vous serez informé de sa progression et de son état dans un e-mail. Si votre demande de port est rejetée par l’opérateur, contactez le [service desk TNS](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) pour obtenir de l’aide.

Pour afficher l’état de votre commande de transfert, dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Commandes de port** **vocales** > , puis sélectionnez **Historique des commandes**. Chaque état de la commande de transfert est répertorié dans la colonne **État** . Pour plus [d’informations, consultez Quel est l’état de vos commandes de transfert ?](port-order-status.md)


## <a name="reporting-telephone-number-issues"></a>Vous signalez des problèmes de numéro de téléphone ?

Si vous remarquez des problèmes avec les numéros transférés dans les 24 à 48 heures qui suivent la fin du port, contactez le [Service Desk TNS](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md). Pour tout problème au-delà de 48 heures, contactez l’équipe Support Microsoft.

## <a name="related-articles"></a>Articles connexes

- [Qu’est-ce qu’une demande de transfert ?](port-order-overview.md)
- [Différents types de numéros de téléphone utilisés pour les offres d'appel](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gérer des numéros de téléphone pour votre entreprise](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Conditions générales relatives aux appels d'urgence](../emergency-calling-terms-and-conditions.md)
- [Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
