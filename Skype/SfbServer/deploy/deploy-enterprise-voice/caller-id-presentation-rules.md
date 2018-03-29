---
title: Création ou modification d’une règle de conversion pour la présentation de l’ID de l’appelant dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Résumé : Apprenez à configurer l’ID de l’appelant pour le panneau de configuration de Business Server à l’aide de la Skype.'
ms.openlocfilehash: b5460558d621b04ca041bd540f9aba9d3a19bd45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server-2015"></a>Création ou modification d’une règle de conversion pour la présentation de l’ID de l’appelant dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à configurer l’ID de l’appelant pour le panneau de configuration de Business Server à l’aide de la Skype.
  
Avec Skype pour Business Server, le numéro de téléphone de la personne appelée (autrement dit, le numéro de téléphone appelé) peuvent être traduites dans le format E.164 dans le format de numérotation locale qui est requis par l' _homologue du tronc_ (autrement dit, la passerelle associée, private branch exchange ( (PBX), ou SIP trunk). À cet effet, vous devez définir une ou plusieurs règles de traduction pour convertir l’URI de demande avant de l’acheminer vers l’homologue de jonction.
  
Skype pour Business Server également vous donne la possibilité à également traduire le numéro de téléphone de l’appelant (autrement dit, le numéro de téléphone qui appelle à partir de l’appelant) à partir du format E.164 dans le format de numérotation locale qui est requis par l’homologue trunk. Par exemple, vous pouvez écrire une règle de conversion pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.
  
### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Pour configurer l’ID de l’appelant pour le panneau de configuration de Business Server à l’aide de Skype

1. Ouvrez Skype pour le panneau de configuration de Business Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
    
3. Dans la page **Configuration de la jonction**, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    
4. Pour configurer la présentation de l’identification de l’appelant :
    
   - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de conversion disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Dans **Règles de conversion du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.
    
   - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, consultez [Définition des règles de traduction](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) dans la documentation de déploiement.
    
   - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, consultez [Définition des règles de traduction](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) dans la documentation de déploiement.
    
   - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, cliquez sur **Copier**, puis sur **Coller**. Pour plus d’informations, consultez [Définition des règles de traduction](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx). 
    
   - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.
    
    > [!CAUTION]
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit. 
  

