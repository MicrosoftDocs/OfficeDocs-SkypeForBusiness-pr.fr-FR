---
title: Créer ou modifier une nouvelle règle de stratégie de version du client
TOCTitle: Créer ou modifier une nouvelle règle de stratégie de version du client
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ898478(v=OCS.15)
ms:contentKeyID: 53095444
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier une nouvelle règle de stratégie de version du client

 

_**Dernière rubrique modifiée :** 2013-01-21_

Les règles de stratégie de version du client définissent les actions qui doivent être entreprises lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques. Vous pouvez créer ou modifier des règles spécifiques pour une stratégie de version du client à partir du Panneau de configuration Lync Server 2013.

> [!IMPORTANT]  
> Les règles sont répertoriées par ordre de priorité. Par exemple, si une règle autorise les clients exécutant la version 1.5 à se connecter et qu’une second règle bloque les clients exécutant une version antérieure à la version 2.0, la première règle est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter.

## Pour créer ou modifier des règles de stratégie de version du client avec le Panneau de configuration Lync Server

1.  [Créer ou modifier une stratégie de version du client](lync-server-2013-create-or-modify-a-new-client-version-policy.md) avec le Panneau de configuration Lync Server.

2.  Dans la page **Modifier la stratégie de version du client**, effectuez l’une des opérations suivantes :
    
      - Cliquez sur **Nouveau** pour créer une règle de version du client.
    
      - Cliquez sur l’un des types de clients définis dans la liste, puis sur **Afficher les détails**.
    
    > [!NOTE]  
    > Vous pouvez utiliser des caractères génériques pour spécifier le type du client.

3.  Dans **Agent utilisateur**, sélectionnez un type de client.

4.  Sous **Numéro de version**, procédez comme suit :
    
      - Dans **Version principale**, tapez le numéro qui correspond à la version principale du client.
    
      - Dans **Version secondaire**, tapez le numéro qui correspond à la version secondaire du client.
    
      - Dans **Version**, tapez le numéro qui correspond aux versions principale et secondaire du client.
    
      - Dans **Mise à jour**, tapez le numéro qui correspond à la version mise à jour du client.
    
    > [!NOTE]  
    > Vous pouvez utiliser des caractères génériques pour spécifier le numéro de version du client.

5.  Pour sélectionner l’opération de comparaison à utiliser pour la version du client spécifiée ci-dessus, dans **Opération de comparaison**, cliquez sur l’une des options suivantes :
    
      - **Identique à**
    
      - **N’est pas**
    
      - **Plus récent que**
    
      - **Plus récent ou identique**
    
      - **Plus ancien que**
    
      - **Plus ancien ou identique**

6.  Pour spécifier l’action à exécuter lorsque les critères définis ci-dessus sont respectés, cliquez sur l’une des options suivantes dans **Action** :
    
      - Pour autoriser le client à se connecter, cliquez sur **Autoriser**.
    
      - Pour autoriser le client à se connecter et à recevoir des mises à jour de Windows Server Update Service ou Microsoft Update, cliquez sur **Autoriser et mettre à niveau**. Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.
        
        > [!NOTE]  
        > Si vous sélectionnez cette action, la prochaine fois que des utilisateurs se connecteront à Lync 2013, une notification s’affichera pour signaler qu’une ou plusieurs mises à jour sont disponibles, même si aucun mise à jour n’a encore été publiée sur Windows Server Update Service ou Microsoft Update. Pour éviter toute confusion, vous avez tout intérêt à choisir cette action uniquement après que des mises à jour ont été mises à disposition.    
      - Pour autoriser le client à se connecter et afficher un message sur l’emplacement de téléchargement d’une autre version du client, cliquez sur **Autoriser avec une URL**. Vous indiquerez l’URL ultérieurement.
    
      - Pour empêcher le client de se connecter, cliquez sur **Bloquer**.
    
      - Pour empêcher le client de se connecter et lui permettre de recevoir des mises à jour de Windows Server Update Service ou Microsoft Update, cliquez sur **Bloquer et mettre à niveau**. Cette action est disponible uniquement lorsque l’agent utilisateur **OC** est sélectionné.
    
      - Pour empêcher le client de se connecter et afficher un message sur l’emplacement de téléchargement d’une autre version du client, cliquez sur **Bloquer avec une URL**. Vous indiquerez l’URL ultérieurement.

7.  (Facultatif) Si vous avez cliqué sur **Autoriser avec une URL** ou **Bloquer avec une URL** à l’étape précédente, dans le champ **URL**, tapez l’URL de téléchargement du client que vous souhaitez inclure dans le message.

8.  Cliquez sur **OK**, puis sur **valider**.

