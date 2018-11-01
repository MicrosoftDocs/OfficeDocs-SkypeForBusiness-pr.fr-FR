---
title: "Spéc. des app. clients pouvant être util. pour la connexion à Lync Server 2013"
TOCtitle: "Spéc. des app. clients pouvant être util. pour la connexion à Lync Server 2013"
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182591(v=OCS.15)
ms:contentKeyID: 49298919
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Spécification des applications clients pouvant être utilisées pour la connexion à Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-12-11_

Lync Server 2013 vous permet de spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions différentes interagissent, les fonctionnalités accessibles à l’un peuvent être limitées par les capacités de l’autre. Pour tirer profit des fonctionnalités incluses dans Lync Server 2013 et améliorer l’expérience globale de l’utilisateur, vous pouvez utiliser le filtre de version du client afin de limiter les versions du client utilisées dans votre environnement Lync Server 2013. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de plusieurs versions du client.

Outre la création d’une stratégie globale, vous pouvez créer des stratégies de version du client pour un service ou un site particulier, ou des stratégies d’étendue d’utilisateur qui peuvent être attribuées à des utilisateurs individuels. La stratégie de version du client avec étendue d’utilisateur peut être attribuée à des utilisateurs individuels du groupe **Utilisateurs** dans le Panneau de configuration Lync Server.

> [!NOTE]  
> Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.

> [!IMPORTANT]  
> Les filtres sont répertoriés par ordre de priorité. Par exemple, si un premier filtre autorise les clients exécutant la version 1.5 à se connecter et qu’un second filtre bloque les clients exécutant une version antérieure à la version 2.0, le premier filtre est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter.

## Pour modifier la stratégie de version du client par défaut

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**.
    
    > [!NOTE]  
    > L’onglet <strong>Stratégie de version du client</strong> est sélectionné par défaut.

4.  Sur la page **Stratégie de version du client**, double-cliquez sur la stratégie **Global** dans la liste.

5.  Dans **Modifier la stratégie de version du client**, effectuez l’une des opérations suivantes :
    
      - Cliquez sur **Nouveau** pour créer une règle de version du client.
    
      - Cliquez sur l’un des types de clients définis dans la liste, puis sur **Afficher les détails**.
    
    > [!NOTE]  
    > Vous pouvez utiliser des caractères génériques pour spécifier le type du client.

6.  Dans **Agent utilisateur**, sélectionnez un type de client.

7.  Sous **Numéro de version**, procédez comme suit :
    
      - Dans **Version principale**, tapez le numéro qui correspond à la version principale du client.
    
      - Dans **Version secondaire**, tapez le numéro qui correspond à la version secondaire du client.
    
      - Dans **Version**, tapez le numéro qui correspond aux versions principale et secondaire du client.
    
      - Dans **Mise à jour**, tapez le numéro qui correspond à la version mise à jour du client.
    
    > [!NOTE]  
    > Vous pouvez utiliser des caractères génériques pour spécifier le numéro de version du client.

8.  Pour sélectionner l’opération de comparaison à utiliser pour la version du client spécifiée ci-dessus, dans **Opération de comparaison**, cliquez sur l’une des options suivantes :
    
      - **Identique à**
    
      - **N’est pas**
    
      - **Plus récent que**
    
      - **Plus récent ou identique**
    
      - **Plus ancien que**
    
      - **Plus ancien ou identique**

9.  Pour spécifier l’action à exécuter lorsque les critères définis ci-dessus sont respectés, cliquez sur l’une des options suivantes dans **Action** :
    
      - Pour autoriser le client à se connecter, cliquez sur **Autoriser**.
    
      - Pour autoriser le client à se connecter et à recevoir des mises à jour de Windows Server Update Service ou Microsoft Update, cliquez sur **Autoriser et mettre à niveau**. Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.
        
        > [!NOTE]  
        > Si vous sélectionnez cette action, la prochaine fois que des utilisateurs se connecteront à Lync 2013, une notification s’affichera indiquant qu’une ou des mises à jour sont disponibles, même si aucun mise à jour n’a encore été publiée sur Windows Server Update Service ou Microsoft Update. Pour éviter toute confusion, vous avez tout intérêt à choisir cette action après que des mises à jour ont été mises à disposition uniquement.    
      - Pour autoriser le client à se connecter et afficher un message sur l’emplacement de téléchargement d’une autre version du client, cliquez sur **Autoriser avec une URL**. Vous indiquerez l’URL ultérieurement.
    
      - Pour empêcher le client de se connecter, cliquez sur **Bloquer**.
    
      - Pour empêcher le client de se connecter et lui permettre de recevoir des mises à jour de Windows Server Update Service ou Microsoft Update, cliquez sur **Bloquer et mettre à niveau**. Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.
    
      - Pour empêcher le client de se connecter et afficher un message sur l’emplacement de téléchargement d’une autre version du client, cliquez sur **Bloquer avec une URL**. Vous indiquerez l’URL ultérieurement.

10. (Facultatif) Si vous avez cliqué sur **Autoriser avec une URL** ou **Bloquer avec une URL** à l’étape précédente, dans le champ **URL**, tapez l’URL de téléchargement du client que vous souhaitez inclure dans le message.

11. Cliquez sur **OK**, puis sur **valider**.

## Voir aussi

#### Autres ressources

[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

