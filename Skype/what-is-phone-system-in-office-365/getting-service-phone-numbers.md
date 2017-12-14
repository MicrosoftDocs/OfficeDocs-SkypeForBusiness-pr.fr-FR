---
title: "Obtention des numéros de téléphone des services Skype Entreprise"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734

description: "Outre obtenir des numéros de téléphone pour des utilisateurs individuels à partir d'Office 365, il est également possible de rechercher et d'acquérir des numéros de téléphone gratuits ou payants pour des services tels que les conférences rendez-vous (pour les ponts de conférence) et les standards automatiques, qui sont des numéros de service appelés. Les numéros de téléphone de service disposent d'une capacité d'appels simultanés plus élevée que les numéros de téléphone d'utilisateur ou d'abonné. Par exemple, un numéro de service peut gérer des centaines d'appels simultanément, alors qu'un numéro de téléphone d'utilisateur ne peut gérer que quelques appels à la fois."
---

# Obtention des numéros de téléphone des services Skype Entreprise

Outre obtenir des numéros de téléphone pour des utilisateurs individuels à partir d'Office 365, il est également possible de rechercher et d'acquérir des numéros de téléphone gratuits ou payants pour des services tels que les conférences rendez-vous (pour les ponts de conférence) et les standards automatiques, qui sont des numéros de service appelés. Les numéros de téléphone de service disposent d'une capacité d'appels simultanés plus élevée que les numéros de téléphone d'utilisateur ou d'abonné. Par exemple, un numéro de service peut gérer des centaines d'appels simultanément, alors qu'un numéro de téléphone d'utilisateur ne peut gérer que quelques appels à la fois.
  
> [!IMPORTANT]
> La consommation RTC doit être configurée pour pouvoir acquérir des numéros gratuits. 
  
Vous pouvez obtenir des numéros de service à utiliser avec Skype Entreprise de deux manières : 
  
- Obtention de nouveaux numéros à partir de Skype Entreprise Office 365.
    
- Transfert de vos numéros existants du fournisseur de services ou de l'opérateur de téléphonie.
    
    > [!NOTE]
    > Lorsque vous transférez vos numéros de service, il est fortement recommandé de contacter le [Contacter le support Office 365 pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) pour vérifier que la capacité d'appels simultanés est comprise et configurée correctement.
  
## Obtenir de nouveaux numéros de service

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans le volet de navigation de gauche, sélectionnez **Voix** > **Numéros de téléphone** > **Ajouter**, puis cliquez sur **Nouveaux numéros de service**.
    
    **IMPORTANT**: pour que l'option **Voix** apparaisse dans le volet de navigation gauche du Centre d'administration Skype Entreprise, vous devez d'abord acheter au moins une **licence Entreprise E5**, une licence de composant additionnel **Système téléphonique**, ou une licence de composant additionnel **Audioconférence**.
    
4. Dans la page **Ajouter de nouveaux numéros de service**, utilisez les listes déroulantes pour sélectionner les éléments suivants :
    
  - **Pays/Région**
    
  - **État/Région**
    
  - **Ville**
    
5. Sous **Quantité**, saisissez le nombre de numéros de téléphone dont vous avez besoin pour votre organisation, puis cliquez sur **Ajouter** pour créer une réservation. Vous avez 10 minutes pour choisir vos numéros de téléphone. Si cela vous prend plus de temps, les numéros de téléphone retournent dans la réserve de numéros de téléphone.
    
    > [!NOTE]
    > Vous pouvez voir le nombre de numéros de téléphone basés sur le nombre de licences répertoriées en regard de **Nombre total d'utilisateurs que vous pouvez acquérir**. 
  
6. Cliquez sur **Afficher les numéros** pour consulter la liste complète des numéros de téléphone. Cela est utile si vous ne voulez pas sélectionner un numéro de téléphone spécifique dans la liste.
    
7. Sélectionnez les numéros de téléphone appropriés, puis cliquez sur **Acquérir les numéros**.
    
### Affecter des numéros de service

Une fois que vous avez vos numéros de service, ces numéros peuvent être affectés à un pont de conférences rendez-vous. Pour ce faire, consultez [Modifier le numéro payant ou numéros gratuits sur le pont de conférence Audio](../audio-conferencing-in-office-365/change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md).
  
### Transférer des numéros de service existants

Si vous voulez transférer des numéros de service depuis votre fournisseur ou opérateur de services actuel, vous devez envoyer une demande de transfert manuellement à Microsoft. Vous devez envoyer différentes demandes de transfert pour chaque type de numéro de service (gratuits et payants) que vous transférez à l'aide d'une lettre d'autorisation (LOA). Dans la lettre d'autorisation (LOA), vous devez sélectionner le bon type de numéro de service. Lorsque vous contactez le support Microsoft, assurez-vous d'indiquer que vous transférez un numéro de service ( *pas un numéro d'utilisateur ou d'abonné*  ) sinon la capacité d'appels simultanés peut ne pas être suffisante pour gérer les volumes d'appels. Si vous voulez en savoir plus sur une demande de transfert envoyée, consultez[Envoi manuel d'une demande de service personnalisé](../what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request.md)
  
## Développez pour connaître combien de numéros de téléphone vous pouvez obtenir.

Lorsque vous recherchez et obtenez des numéros de téléphone pour votre organisation, vous pouvez obtenir plus de numéros de téléphone que de licences affectées. Cela dépend toutefois des types de numéros de téléphone que vous avez achetés et des types de licences que vous avez affectées.
  
Vous pouvez afficher le nombre de numéros de téléphone qu'il est possible d'obtenir sur la page **Numéros de téléphone** du centre d'administration de Skype Entreprise ou exécutez l'applet de commande[Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/en-us/library/mt634605.aspx). 
  
> [!IMPORTANT]
> Les limites ci-dessous n'incluent pas les numéros transférés vers Microsoft. 
  
||||
|:-----|:-----|:-----|
|**Les types de numéros de téléphone sont les suivants.** <br/> |**Comment obtenir le nombre total de numéros de téléphone ?** <br/> |**Voici un exemple :** <br/> |
|Numéro d'utilisateur (abonné)  <br/> |Le nombre de numéros de téléphone est égal au nombre total de licences de plan d'appels vocaux  *nationaux + nationaux et internationaux*  multiplié par 1,1 + 10 numéros de téléphone supplémentaires. <br/> |Si vous avez 50 utilisateurs au total avec des plans d'appels vocaux nationaux et internationaux, vous pouvez acheter **65** numéros de téléphone **(50 x 1,1 + 10)**. <br/> |
|Numéro de service payant  <br/> | Le nombre de numéros de téléphone est égal au nombre total de licences *PBX Cloud + de conférence RTC*  et suit les conditions suivantes : <br/>  Si **1 à 25 licences** sont affectées, **5** numéros de téléphone sont attribués. <br/>  Si **26 à 49 licences** sont affectées, **10** numéros de téléphone sont attribués. <br/>  Si **50 à 99 licences** sont affectées, **20** numéros de téléphone sont attribués. <br/>  Si **100 à 149 licences** sont affectées, **30** numéros de téléphone sont attribués. <br/>  Si **150 à 199 licences** sont affectées, **40** numéros de téléphone sont attribués. <br/>  Si **200 à 499 licences** sont affectées, **65** numéros de téléphone sont attribués. <br/>  Si **500 à 749 licences** sont affectées, **90** numéros de téléphone sont attribués. <br/>  Si **750 à 999 licences** sont affectées, **110** numéros de téléphone sont attribués. <br/>  Si **1 000 à 1 249 licences** sont affectées, **125** numéros de téléphone sont attribués. <br/>  Si **1 250 à 1 499 licences** sont affectées, **135** numéros de téléphone sont attribués. <br/>  Si **1 500 à 1 999 licences** sont affectées, **160** numéros de téléphone sont attribués. <br/>  Si **2 000 à 2 999 licences** sont affectées, **210** numéros de téléphone sont attribués. <br/>  Si **3 000 à 6 999 licences** sont affectées, **420** numéros de téléphone sont attribués. <br/>  Si **7 000 à 9 999 licences** sont affectées, **500** numéros de téléphone sont attribués. <br/>  Si **10 000 à 14 999 licences** sont affectées, **600** numéros de téléphone sont attribués. <br/>  Si **15 000 à 19 999 licences** sont affectées, **700** numéros de téléphone sont attribués. <br/>  Si **20 000 à 49 999 licences** sont affectées, **1 000** numéros de téléphone sont attribués. <br/>  Si **+ de 50 000 licences** sont affectées, **1 500** numéros de téléphone sont attribués. <br/> |Si vous avez un total de **51** licences PBX Cloud et de conférence RTC, vous pouvez obtenir **20** numéros de service payants. <br/> |
|Numéro de service gratuit  <br/> | Le nombre de numéros de téléphone est égal au nombre total de licences *PBX Cloud + de conférence RTC*  et suit les conditions suivantes : <br/>  Si **1 à 25 licences** sont affectées, **5** numéros de téléphone sont attribués. <br/>  Si **26 à 49 licences** sont affectées, **10** numéros de téléphone sont attribués. <br/>  Si **50 à 99 licences** sont affectées, **20** numéros de téléphone sont attribués. <br/>  Si **100 à 149 licences** sont affectées, **30** numéros de téléphone sont attribués. <br/>  Si **150 à 199 licences** sont affectées, **40** numéros de téléphone sont attribués. <br/>  Si **200 à 499 licences** sont affectées, **65** numéros de téléphone sont attribués. <br/>  Si **500 à 749 licences** sont affectées, **90** numéros de téléphone sont attribués. <br/>  Si **750 à 999 licences** sont affectées, **110** numéros de téléphone sont attribués. <br/>  Si **1 000 à 1 249 licences** sont affectées, **125** numéros de téléphone sont attribués. <br/>  Si **1 250 à 1 499 licences** sont affectées, **135** numéros de téléphone sont attribués. <br/>  Si **1 500 à 1 999 licences** sont affectées, **160** numéros de téléphone sont attribués. <br/>  Si **2 000 à 2 999 licences** sont affectées, **210** numéros de téléphone sont attribués. <br/>  Si **3 000 à 6 999 licences** sont affectées, **420** numéros de téléphone sont attribués. <br/>  Si **7 000 à 9 999 licences** sont affectées, **500** numéros de téléphone sont attribués. <br/>  Si **10 000 à 14 999 licences** sont affectées, **600** numéros de téléphone sont attribués. <br/>  Si **15 000 à 19 999 licences** sont affectées, **700** numéros de téléphone sont attribués. <br/>  Si **20 000 à 49 999 licences** sont affectées, **1 000** numéros de téléphone sont attribués. <br/>  Si **+ de 50 000 licences** sont affectées, **1 500** numéros de téléphone sont attribués. <br/> |Si vous avez un total de **1001** licences PBX Cloud et de conférence RTC, vous pouvez obtenir **125** numéros de service gratuits. <br/> > [!IMPORTANT]> La [Configurer les Communications crédits pour votre organisation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) est requise pour réserver et utiliser des numéros de téléphone gratuits.          |
   
> [!NOTE]
> Si vous devez obtenir plus de numéros de téléphone, vous pouvez contacter le [Contacter le support Office 365 pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). 
  
## Rubriques connexes

[Conditions générales relatives aux appels d'urgence](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)
  
[Période de sortant gratuit de audio conférence](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  

