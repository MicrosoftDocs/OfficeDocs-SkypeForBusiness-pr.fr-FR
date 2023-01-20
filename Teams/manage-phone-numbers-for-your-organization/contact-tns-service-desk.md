---
title: Contacter l’équipe des services de numéros de téléphone
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.tnsservicedesk
- ms.teamsadmincenter.voice.contacttnssupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: Lorsque vous obtenez des numéros de téléphone ou des numéros de port (transfert) pour votre organisation, vous devrez peut-être obtenir de l’aide et du support auprès du support technique TNS.
ms.openlocfilehash: 9984775a05458592fe1789c0dd8b173a08783220
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835557"
---
# <a name="telephone-number-services-tns---service-desk"></a>Services de numéro de téléphone (TNS) - Service Desk

> [!NOTE]
> Depuis le 22 juillet 2021, le système de courrier électronique précédent pour contacter le service de TNS a été mis hors service.

Il existe un nouveau processus pour interagir avec le service TNS (Telephone Number Services) à partir de notre nouveau centre de services de **[numéro de téléphone](https://pstnsd.powerappsportals.com)**. Vous pouvez désormais ouvrir des tickets, afficher des tickets et suivre la communication dans un emplacement unique intégré au Centre d’administration Teams. Ces tâches sont décrites plus en détail dans les sections suivantes.


- **[Créer un cas](#create-a-new-case)** : envoyez une nouvelle demande ou une demande générale.

- **[Afficher mes cas existants](#view-and-manage-existing-cases)** : suivez et surveillez vos cas existants.

- **[Afficher mes cas d’entreprise](#view-and-manage-existing-cases)** : suivez et surveillez les cas existants de votre entreprise. Si vos collègues de votre entreprise ont ouvert des cas, vous pouvez les consulter dans cet affichage.

- **[Envoyez vos commentaires](#view-and-manage-existing-cases)** : partagez vos commentaires avec nous.

## <a name="create-a-new-case"></a>Créer un nouveau cas

> [!NOTE]
> Seule une personne du même locataire est autorisée à créer un cas. Par exemple, une personne de @fabrikam.com ne peut pas créer de cas pour le compte de @contoso.com.

Pour créer un cas, procédez comme suit :

1. Sélectionnez **Créer un cas** à partir de l’un des emplacements suivants :

   - À partir de la page d’accueil **du Centre de services de numéro de téléphone** , en haut de la page ou en bas de la vignette.

   - À partir de la page **Afficher mes cas existants**  .

   - À partir de la page **Afficher les cas de mon entreprise** .

2. Fournissez les détails de votre cas comme décrit en détail dans la [section suivante](#provide-case-details).

3. Après avoir entré toutes les valeurs, sélectionnez **Envoyer**. Vous verrez un nouvel écran dans lequel vous pouvez voir votre numéro de cas.

### <a name="provide-case-details"></a>Fournir les détails du cas

Pour comprendre les détails du cas, Microsoft a besoin des informations suivantes :

- [Catégorie de cas](#case-category)
- [Pays ou région](#country-or-region)
- [Type de cas](#case-type)
- [Titre de cas](#case-title)
- [Contacts supplémentaires pour les notifications](#additional-contacts-for-notifications)
- [Description](#description)
- [Documents de prise en charge supplémentaires](#additional-supporting-documents)

#### <a name="case-category"></a>Catégorie de cas

Un cas peut avoir l’une des deux catégories suivantes :

- **Soumettre une nouvelle demande**- Choisissez cette option si vous souhaitez envoyer une nouvelle demande. Par exemple, vous souhaitez envoyer une demande de port ou acheter des numéros de téléphone auprès de Microsoft.

- **Demande générale** : choisissez cette option si vous avez des questions qui vous aideront à déterminer votre demande. Par exemple, vous devez savoir si vous pouvez porter vos numéros sans fil vers Microsoft ou si Microsoft prend en charge les numéros gratuits personnalisés.

#### <a name="country-or-region"></a>Pays ou région

Sélectionnez le pays/la région pour lequel vous soumettez ce cas. Si vous avez des demandes pour plusieurs pays, vous devez ouvrir un cas par pays/région.

#### <a name="case-type"></a>Type de cas

Le type de cas peut être l’un des suivants :

- **Nom d’appel personnalisé (ÉTATS-UNIS uniquement)** : définissez un nom d’appel personnalisé sur vos numéros de téléphone Microsoft. Cela s’applique uniquement aux numéros de téléphone États-Unis.

  - **Nom d’appel personnalisé à définir (15 caractères uniquement)** : nom d’appel personnalisé que vous souhaitez définir. Le nom a une limite maximale de 15 caractères.

  - **Liste des numéros de téléphone** : liste des numéros de téléphone pour lesquels vous souhaitez définir une valeur de nom d’appel personnalisée. Joignez un fichier csv avec la liste des numéros de téléphone.

- **Port inter-client**– déplacer des numéros de téléphone d’un client à un autre. Par exemple, vous avez deux clients différents au sein de Microsoft et vous souhaitez déplacer vos numéros de téléphone d’un client vers l’autre.

  - **Nom de domaine du client source** : le client à partir duquel vous souhaitez déplacer des numéros de téléphone vers un autre client.

  - **Identificateur unique du client source** : ID du client pour le client source. Ce champ est facultatif.

  - **Nom de domaine du client de destination** : le client vers lequel vous souhaitez déplacer des numéros de téléphone.

  - **Identificateur unique du client de destination** : ID client pour le client de destination. Ce champ est facultatif.

  - **Date et heure demandées*** : date et heure auxquelles vous souhaitez déplacer vos numéros du client source vers le client de destination. Consultez Date et heure.

  - **Liste des numéros de téléphone** : liste des numéros de téléphone que vous souhaitez déplacer du client source vers le client de destination. Joignez un fichier csv avec la liste des numéros de téléphone.

- **Modification du type d’inventaire**– Modifier le type de numéro de téléphone. Par exemple, vous souhaitez remplacer vos numéros d'utilisateur Microsoft par des numéros de service. Pour plus d’informations sur les types de numéros de téléphone pris en charge par Microsoft, consultez [Types de numéros de téléphone](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Convertir en** - Sélectionnez cette option pour convertir vos numéros en numéros d’utilisateur ou en numéros de service.

  - **Date/heure souhaitée*** : date et heure auxquelles vous souhaitez modifier le type d’inventaire de vos numéros. Pour plus d’informations, consultez Date et heure.

  - **Case à cocher : je comprends que pour pouvoir mettre à jour le type d’inventaire, mes numéros de téléphone doivent être désaffectés** . Microsoft ne peut pas traiter les demandes de modification de type de numéro de téléphone, sauf si les numéros de téléphone de votre locataire ne sont pas attribués. Si vous demandez cette modification pour une date ultérieure, vous devez vous assurer que les numéros ne sont pas attribués avant la date et l’heure que vous avez demandées.

  - **Liste des numéros de téléphone** : liste des numéros de téléphone dont vous souhaitez modifier le type. Joignez un fichier csv avec la liste des numéros de téléphone.

- **Nouvelle acquisition TN**– Achetez de nouveaux numéros de téléphone auprès de Microsoft.

  - **Type de numéros** - Sélectionnez le type de vos nombres. Consultez [Types de numéros de téléphone](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Vous avez essayé d’obtenir des numéros de téléphone à partir du portail Teams Administration Center** - Avez-vous essayé d’acheter ces numéros de téléphone à partir du Centre Administration Microsoft Teams ?

  - **Quantité de numéros de téléphone requis** : nombre de numéros de téléphone que vous souhaitez acheter.

  - **State/Province/province** : état/province au sein de votre pays/région pour lequel vous souhaitez obtenir des numéros de téléphone.

  - **City** : ville au sein de l’état/province pour lequel vous souhaitez obtenir des numéros de téléphone.

  - **Adresse de votre bureau** : cela est spécifique à certains pays uniquement. Il s’agit de l’adresse de votre bureau.

  - **Référencement au répertoire** : ceci est spécifique à certains pays uniquement. Voulez-vous publier les informations de votre entreprise avec les numéros de téléphone ?

- **Porter vers** – Porter les numéros de téléphone existants de votre fournisseur de services actuel vers Microsoft.

  - **Nommez votre demande de port** : fournissez un nom facile à mémoriser pour votre demande de port.

  - **Date/heure de portage demandée*** : date et heure auxquelles vous souhaitez que les numéros soient transférés vers Microsoft. Il ne s’agit pas d’une date de portage garantie, car le propriétaire du numéro actuel doit d’abord approuver notre demande de port. Consultez Date et heure.

  - **Liste des numéros à porter** : liste des numéros de téléphone que vous souhaitez porter vers Microsoft. Joignez un fichier csv avec la liste des numéros de téléphone.

  - **Courrier d'autorisation (LOA)** : joignez un courrier d'autorisation signé et rempli ici. Microsoft ne peut pas traiter une demande de port sans courrier d’autorisation.

    > [!NOTE]
    > Pour plus d’informations sur les contrats d’accès pour le port/le transfert de numéros de téléphone existants et les exigences de documentation supplémentaires, consultez [Gérer les numéros de téléphone pour le forfait d’appels](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).
    >
    >Pour transférer ou transférer des numéros de téléphone 999 ou moins pour vos utilisateurs, chargez les LBA terminés et signés dans le Centre d’administration Microsoft Teams pour un traitement ultérieur.
    >
    > Pour porter/transférer plus de 999 numéros de téléphone ou si vous rencontrez des problèmes avec le processus de portage dans le centre d’administration Microsoft Teams, vous pouvez [envoyer manuellement une commande de transfert](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) au Service Desk TNS pour votre région.

- **Mise à jour d’adresse** – Mettre à jour l’adresse d’appel d’urgence. Notez que ce champ s’applique uniquement à certains pays.

  - **Id d’emplacement** : ID d’emplacement de votre adresse d’urgence.

  - **Liste des numéros de téléphone** : liste des numéros de téléphone pour lesquels vous souhaitez modifier l’adresse d’urgence (entrez l’adresse souhaitée dans le champ Description). Joignez un fichier csv avec la liste des numéros de téléphone.

**Date et heure.** Si vous sélectionnez Pays = France, date = 14/08/2021 et heure = 10h00, la demande sera exécutée le 14/08/2021 à 10h00. Heure française.

#### <a name="case-title"></a>Titre de l’incident

Entrez un titre qui résume votre demande.

#### <a name="additional-contacts-for-notifications"></a>Contacts supplémentaires pour les notifications

Entrez la liste des personnes qui recevront des notifications de status automatisées de Microsoft.
Par exemple, vous souhaitez soumettre une demande de portage et vous souhaitez que deux autres collègues, en plus de vous-même, reçoivent des notifications de status automatisées. Indiquez les adresses e-mail de vos collègues dans la section **Notification par e-mail**. Ces informations sont facultatives.

#### <a name="description"></a>Description

Décrivez ce que vous essayez d’atteindre et répertoriez vos questions pour le service TNS (Microsoft Telephone Number Services).

#### <a name="additional-supporting-documents"></a>Documents de prise en charge supplémentaires

Chargez tous les documents supplémentaires pour votre cas.

## <a name="view-and-manage-existing-cases"></a>Afficher et gérer les cas existants

Vous pouvez afficher vos cas en sélectionnant **Afficher mes cas existants** et en sélectionnant le numéro de cas. La sélection d’un numéro de cas vous redirige vers les détails du cas. (Vous pouvez également afficher les cas d’entreprise en sélectionnant **Afficher les cas d’entreprise**.)  Vous pouvez également :

- **Filtrez vos cas** en sélectionnant **Cas ouverts**,  **Tous les cas**, ou **Cas fermés**.

- **Communiquez avec le service desk TNS** concernant votre cas en ouvrant un cas existant, en faisant défiler vers le bas et en sélectionnant **Ajouter un commentaire**. Une nouvelle fenêtre s’affiche. Entrez votre message dans la zone de commentaire. Joignez tous les documents de support (le cas échéant), puis sélectionnez **Envoyer**.

  Les réponses du **service desk TNS** s’affichent dans la même chronologie. En cas de mise à jour de votre cas, vous recevez une notification par e-mail automatisée de la mise à jour.

- **Annuler une cas** en accédant à un cas existant, en faisant défiler vers le bas, et en sélectionnant **Annuler le cas.** Sélectionnez une raison pour l’annulation dans la liste déroulante, puis sélectionnez **Annuler**.

- **Résoudre un cas** : si vous pensez que votre demande est terminée, vous pouvez résoudre un cas en accédant à un cas existant, en faisant défiler vers le bas, et en sélectionnant **Résoudre le cas**. Sélectionnez **Fermer**; le cas s’affiche désormais comme **Résolu – Problème résolu**.

## <a name="related-topics-and-additional-resources"></a>Rubriques connexes et ressources supplémentaires

- Pour obtenir de l’aide sur la mise en place et la configuration des numéros, les licences, les frais ou la facturation, consultez [Contact de support pour les produits professionnels - Aide de l’administrateur](/microsoft-365/admin/contact-support-for-business-products?tabs=online).

- Pour plus d’informations sur les forfaits d’appels disponibles dans votre pays/région, consultez la[Disponibilité des pays et de la région pour l’audioconférence et les forfaits d’appels](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

- Pour plus d’informations sur le ou les types de numéros de téléphone appropriés pour votre organisation, consultez [Différents types de numéros de téléphone](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

- Pour plus d’informations sur la gestion des numéros de téléphone de votre organisation, consultez [Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-for-your-organization.md).

- Pour plus d’informations sur les conditions générales d’appel d’urgence, consultez [Conditions générales d’appel d’urgence](../emergency-calling-terms-and-conditions.md).
