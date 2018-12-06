---
title: 'Lync Server 2013 : Vérification de la réplication de schéma'
TOCTitle: Vérification de la réplication de schéma
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412822(v=OCS.15)
ms:contentKeyID: 49298502
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de la réplication de schéma Active Directory dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-29_

Avant d’exécuter la préparation de la forêt, vérifiez manuellement que la partition du schéma a été répliquée.

## Pour vérifier manuellement la réplication de schéma

1.  Ouvrez une session sur un contrôleur de domaine en tant que membre du groupe Administrateurs d’entreprise.

2.  Ouvrez l’éditeur ADSI en cliquant sur **Démarrer** , sur **Outils d’administration** , puis sur **Modification ADSI** .
    
    > [!TIP]  
    > Vous pouvez également exécuter <strong>adsiedit.msc</strong> à partir de la ligne de commande.

3.  Dans l’arborescence de la console MMC (Microsoft Management Console), cliquez sur **Modification ADSI** si cette option n’a pas encore été sélectionnée.

4.  Dans le menu **Action** , cliquez sur **Connexion** .

5.  Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu** , sélectionnez **Schéma** , puis cliquez sur **OK** .

6.  Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion. Si cet objet existe, si la valeur de l’attribut **rangeUpper** est 1150, si la valeur de l’attribut **rangeLower** est 3, cela signifie que le schéma a été mis à jour et répliqué avec succès. Si cet objet n’existe pas ou si la valeur des attributs **rangeUpper** et **rangeLower** n’est pas spécifiée, cela signifie que le schéma n’a pas été modifié ou n’a pas été répliqué.

## Voir aussi

#### Tâches

[Exécution de la préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-running-schema-preparation.md)  

#### Concepts

[Préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

