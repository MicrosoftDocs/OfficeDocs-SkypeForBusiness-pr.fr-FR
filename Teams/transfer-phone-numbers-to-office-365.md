---
title: Transférer les numéros de téléphone vers Office 365
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 47b3af8e-4171-4dec-8333-c956f108664e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PortingNumbersOverview
ms.custom:
- Calling Plans
- LIL_Placement
description: Learn what you need to know and do before porting phone numbers to Skype for Business, and how to create a port order to transfer them.
ms.openlocfilehash: 7b61ff671814e0c4ce46cb8492930ada73a8e5fe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298227"
---
# <a name="transfer-phone-numbers-to-office-365"></a>Transférer les numéros de téléphone vers Office 365

Il est facile de transférer vos numéros de téléphone à partir de votre fournisseur de services actuel vers Skype Entreprise. Après avoir transféré vos numéros de téléphone vers Skype Entreprise, Microsoft devient votre fournisseur de services et vous facture pour l'utilisation de ces numéros de téléphone.
  
Avant de commencer à transférer des numéros de téléphone, nous vous conseillons de passer en revue les informations contenues dans [transfert des numéros de téléphone questions fréquentes](transferring-phone-numbers-common-questions.md). Si vous disposez de numéros de service pour les ponts de conférence rendez-vous, les standards automatiques ou d’autres numéros de service, les numéros de téléphone gratuits ou dont vous avez plus de 999 (abonné) à transférer vers Skype entreprise, reportez-vous à la rubrique [gestion des numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) doit télécharger les formulaires appropriés et nous les envoyer.

  > [!NOTE]
  > Les commandes de port ne sont traitées pour le transfert des numéros de téléphone que sur les jours ouvrés américains et non sur les jours fériés ou les week-end. 
  
## <a name="how-to-create-a-port-order-and-transfer-your-phone-numbers-to-skype-for-business"></a>Création d'une demande de transfert et transfert de vos numéros de téléphone vers Skype Entreprise
<a name="bk_LNPcountries_1"> </a>

  > [!NOTE]
  > Si vous disposez de numéros de service pour les ponts de conférence rendez-vous, les standards automatiques ou d’autres numéros de service, les numéros de téléphone gratuits ou dont vous avez plus de 999 (abonné) à transférer vers Skype entreprise, reportez-vous à la rubrique [gestion des numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) pour sélectionner le pays ou la région approprié et télécharger les formulaires appropriés et nous les envoyer.
 
![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise**

 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.
    
3. Dans le volet de navigation de gauche, sélectionnez **Voix** > **Commandes de transfert** > cliquez sur **Ajouter**.
    
4. Dans la page **Demande de transfert de nouveaux numéros locaux**, lisez les informations, puis cliquez sur **Commençons**.
    
5. Dans la page **Informations sur le compte**, entrez les informations ci-dessous, puis cliquez sur **Suivant**:
    
   - **Numéro de compte** Numéro de compte du fournisseur de services ou de l'opérateur.
    
   - Le **numéro de téléphone de facturation** doit être au format E.164 (un signe + est obligatoire comme préfixe du numéro). Par exemple, pour un numéro en Amérique du Nord, utilisez le format + 1XXXYYYZZZZ.
    
   - **Code confidentiel pour débloquer le numéro** Code confidentiel : si nécessaire pour votre fournisseur de services ou votre opérateur actuel.
    
   - **Nom de la société** Il s'agit du nom de votre entreprise ou organisation.
    
     > [!NOTE]
     > La zone **Nom de la société** n'accepte que 25 caractères, espaces compris. Si le nom de la société comporte plus de 25 caractères, les 25 premiers caractères sont envoyés et la demande de transfert est traitée malgré tout.
  
   - **Personne autorisant** Nom de l'utilisateur autorisé
    
     > [!NOTE]
     > La zone **Personne autorisant** n'accepte que 15 caractères, espaces compris. Si le nom de la personne autorisant contient plus de 15 caractères, les 15 premiers caractères sont envoyés et la demande de transfert est traitée malgré tout.
  
   - **Adresse du service** Adresse du service pour le compte. Elle figurera sur la facture de votre fournisseur ou de votre opérateur de services.
    
   - **Ville**, **État**, **Code postal** de l'adresse du service.
    
6. Dans la page **Numéros**, entrez les numéros de téléphone que vous souhaitez transférer au format E.164. Par exemple, pour un numéro en Amérique du Nord, utilisez le format + 1XXXYYYZZZZ. Utilisez une virgule pour séparer plusieurs numéros de téléphone.
    
    > [!NOTE]
    > Si vous effectuez un transfert complet, vous devez inclure le numéro de téléphone de facturation du service dans la liste. Pour un transfert partiel, n'indiquez pas le numéro de téléphone de facturation dans cette liste. 
  
    Si vous effectuez un transfert complet, sélectionnez **Je transfère tous mes numéros à partir de mon opérateur actuel**. Si vous effectuez un transfert partiel, sélectionnez **Je transfère seulement certains de mes numéros**. Une fois que vous avez sélectionné le numéro, cliquez sur **Vérifier la portabilité des numéros**.
    
7. Cliquez sur **Continuer**.
    
8. Dans la **page Date de transfert** , dans **** la liste déroulante jour, sélectionnez la date, puis dans la liste déroulante **heure de début** , sélectionnez l’heure (heure de la côte est), puis cliquez sur **suivant**.
    
9. On the **Letter of authorization** page, check each of the following boxes. Then under the **Signature** box, type the person that is authorized to make changes to the account. This is the same name that is used on the **Account Information** page > **Authorizing person**. Then click **Next**.
    
10. Sur la page **Soumettre**, sous **Autres personnes à notifier**, indiquez les adresses électroniques des personnes de votre choix et cliquez sur **Soumettre la demande de transfert**. La demande de transfert est désormais répertoriée sur la page **Demandes de transfert**. Vous pouvez afficher l'état de la demande sous la colonne **État**. Vous pouvez consulter les détails de la demande de transfert tels que l' **ID de demande**, la **soumission**, la **date de transfert** et l' **état**. Vous pouvez voir plus de détails relatifs à la demande de transfert dans le panneau Action, notamment le nom de l'opérateur téléphonique.
    
## <a name="what-happens-next"></a>Que va-t-il se passer ensuite ?
<a name="bk_LNPcountries_1"> </a>

Une fois votre demande de transfert déposée et reçue, vous recevez un courrier électronique confirmant votre demande de transfert. 
  
Your port order request will be checked and updated daily and you will be notified of its progress and status in email. If your request is rejected, you will be asked to open a support ticket and in that support ticket we ask that you provide **Port Order ID**. The port order ID can be found in the Skype for Business admin center under **Voice** > **Port orders** > **Order ID** column.
  
## <a name="what-if-i-have-problems"></a>Que faire en cas de problème ?
<a name="bk_LNPcountries_1"> </a>

 **L'adresse du service est différente de l'adresse de facturation. Les informations d'adresse figurant dans la commande correspondent à celles de la facture. Pourquoi la commande continue-t-elle à être rejetée ?** La plupart des opérateurs se basent sur l'adresse du service et non sur l'adresse de facturation pour identifier les informations de transfert. Comme une facture est une imputation comptable, elle peut ne pas comporter les mêmes informations que l'adresse du service des numéros transférés.
  
 **Que faire si le traitement de ma demande est trop long ?** Nous souhaitons que le transfert de numéros soit une procédure simple et rapide. Si le traitement de votre demande prend plus longtemps que vous ne le pensez et que le centre d'administration Skype Entreprise indique que l'état est incomplet, ouvrez un ticket d'assistance pour y indiquer l'ID de demande de transfert.

   
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 