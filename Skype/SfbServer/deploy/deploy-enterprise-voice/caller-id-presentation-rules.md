---
title: Création ou modification d’une règle de traduction pour une présentation d’identification d’appelant dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Résumé: Découvrez comment configurer l’identification de l’appelant à l’aide du panneau de configuration Skype entreprise Server.'
ms.openlocfilehash: ca35b3398732296f435196ffeb38d915472b303d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233766"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Création ou modification d’une règle de traduction pour une présentation d’identification d’appelant dans Skype entreprise Server

**Résumé:** Découvrez comment configurer l’identification de l’appelant à l’aide du panneau de configuration Skype entreprise Server.

Avec Skype entreprise Server, le numéro de téléphone de la personne appelé (c’est-à-dire, le numéro de téléphone appelé) peut être converti à partir du format E. 164 au format de numérotation local requis par l’homologue de _Trunk_ (c’est-à-dire, la passerelle associée, l’échange de succursales privées (). PBX ou SIP Trunk). À cet effet, vous devez définir une ou plusieurs règles de traduction pour convertir l’URI de demande avant de l’acheminer vers l’homologue de jonction.

Skype entreprise Server vous permet également de traduire le numéro de téléphone de l’appelant (c’est-à-dire, le numéro de téléphone à partir duquel l’appelant appelle) le format E. 164 au format de numérotation local requis par l’homologue Trunk. Par exemple, vous pouvez écrire une règle de conversion pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Pour configurer l’identification de l’appelant à l’aide du panneau de configuration Skype entreprise Server

1. Ouvrez le panneau de configuration Skype entreprise Server.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

3. Dans la page **Configuration de la jonction**, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.

4. Pour configurer la présentation de l’identification de l’appelant :

   - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Règles de conversion du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une règle, voir [définition des règles de traduction](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) dans la documentation de déploiement.

   - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) de la documentation de déploiement.

   - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, cliquez sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à la rubrique [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

     > [!CAUTION]
     > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.


