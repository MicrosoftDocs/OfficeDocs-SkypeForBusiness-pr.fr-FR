---
title: Créer ou modifier une règle de traduction pour la présentation de l’ID d’appelant dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Résumé : Découvrez comment configurer l’ID de l’appelant à l’aide Skype Entreprise Server panneau de configuration.'
ms.openlocfilehash: 0bef5929c48e7b86cdc4ccf0fe7f4096733e78df
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742880"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Créer ou modifier une règle de traduction pour la présentation de l’ID d’appelant dans Skype Entreprise Server

**Résumé :** Découvrez comment configurer l’ID de l’appelant à l’aide Skype Entreprise Server panneau de configuration.

Avec Skype Entreprise Server, le numéro de téléphone de l’appelé (c’est-à-dire, le numéro de téléphone appelé) peut être  converti du format E.164 au format de numérotation local requis par l’homologue de la connexion (c’est-à-dire, la passerelle associée, le PBX ou la connexion SIP). Pour ce faire, vous devez définir une ou plusieurs règles de traduction pour traduire l’URI de demande avant de l’acheminer vers l’homologue de jonction.

Skype Entreprise Server vous permet également de traduire le numéro de téléphone de l’appelant (c’est-à-dire, le numéro de téléphone de l’appelant) du format E.164 au format de numérotation local requis par l’homologue de la connexion. Par exemple, vous pouvez écrire une règle de traduction pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Pour configurer l’ID de l’appelant à l’aide Skype Entreprise Server panneau de configuration

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

3. Dans la page **Configuration de la jonction**, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.

4. Pour configurer la présentation de l’identification de l’appelant :

   - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de traduction disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Dans **Règles de traduction du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, voir  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.

   - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, voir [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) dans la documentation de déploiement.

   - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, voir [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).

   - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.

     > [!CAUTION]
     > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.