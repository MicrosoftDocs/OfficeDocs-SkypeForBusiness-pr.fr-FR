---
title: Configuration de la passerelle XMPP sur Lync Server 2013
description: Configurez la passerelle XMPP sur Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78765237e737dea29d77230d6b0eecdb0348cb41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542950"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Configuration de la passerelle XMPP sur Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-28_

Les dernières étapes de la migration de votre passerelle XMPP sont la configuration des certificats pour le serveur Edge Lync Server 2013, le déploiement de la passerelle XMPP Lync Server 2013 et la mise à jour des enregistrements DNS pour la passerelle XMPP. Ces étapes doivent être effectuées en parallèle pour réduire le temps d’arrêt de votre passerelle XMPP. Tous les utilisateurs doivent être déplacés vers votre déploiement Microsoft Lync Server 2013 avant d’effectuer ces étapes.

<div class=" ">


> [!IMPORTANT]  
> La Fédération XMPP n’est pas prise en charge pour les utilisateurs hébergés sur les Survivable Branch Appliances. Cela s’applique à la fois aux informations de présence et à l’échange de messages INSTANTANÉs.



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Configurer des certificats pour la passerelle XMPP sur le serveur Edge Lync Server 2013

1.  Sur le serveur Edge, dans l’Assistant Déploiement, à côté d’**Étape 3 : Demander, installer ou assigner les certificats**, cliquez sur **Réexécuter**.
    
    <div class=" ">
    

    > [!TIP]  
    > Si vous déployez pour la première fois le serveur Edge, l’option Exécuter s’affiche au lieu de Réexécuter.

    
    </div>

2.  Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.

3.  Dans la page **Demande de certificat**, cliquez sur **Certificat de serveur Edge externe**.

4.  Dans la page **Demande différée ou immédiate**, cochez la case **Préparer la demande maintenant, mais l’envoyer plus tard**.

5.  Dans la page **fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, c : \\ CERT \_ exernal \_ Edge. cer).

6.  Dans la page **Spécifier un autre modèle de certificat**, pour utiliser un autre modèle que le modèle WebServer par défaut, cochez la case **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée**.

7.  Dans la page **Nom et paramètres de sécurité**, procédez comme suit :
    
    1.  Dans **Nom convivial**, tapez un nom d’affichage du certificat.
    
    2.  Dans **Longueur en bits**, spécifiez la longueur en bits (la valeur par défaut est 2048).
    
    3.  Vérifiez que la case **Marquer la clé privée du certificat comme exportable** est cochée.

8.  Dans la page **Informations relatives à l’organisation**, tapez le nom de l’organisation et de l’unité d’organisation (par exemple, une division ou un service).

9.  Dans la page **Informations géographiques**, spécifiez les informations d’emplacement.

10. Dans la page **Nom du sujet/Autres noms du sujet**, le système affiche les informations automatiquement renseignées par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les dans les deux étapes suivantes.

11. Sur la page **paramètre du domaine SIP sur les autres noms du sujet** , activez la case à cocher domaine pour ajouter un SIP.\<sipdomain\> entrée de la liste des autres noms du sujet.

12. Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.
    
    <div class=" ">
    

    > [!TIP]  
    > Si le proxy XMPP est installé, le nom de domaine par défaut (par exemple, contoso.com) est mentionné dans les entrées du SAN. Si vous nécessitez d’autres entrées, ajoutez-les pendant cette étape.

    
    </div>

13. Dans la page **Résumé de la demande**, vérifiez les informations de certificat à utiliser pour générer la demande.

14. Une fois les commandes entièrement exécutées, vous pouvez **Afficher le journal** ou cliquer sur Suivant pour continuer.

15. Dans la page **Fichier de demande de certificat **, vous pouvez afficher le fichier de demande de signature de certificat (CSR) généré en cliquant sur **Afficher ** ou quitter l’Assistant Certificat en cliquant sur **Terminer **.

16. Copiez le fichier de la demande et transmettez-le à votre autorité de certification publique.

17. Après la réception, l’importation et l’affectation du certificat public, vous devez redémarrer les services du serveur Edge. Pour cela, tapez dans la console de gestion Lync Server.
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Configurer une nouvelle passerelle XMPP Lync Server 2013

1.  Ouvrez le Panneau de configuration Lync Server.

2.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Partenaires fédérés XMPP**.

3.  Pour créer une configuration, cliquez sur **Nouvelle**.

4.  Définissez les paramètres suivants :

5.  **Domaine principal**     (Obligatoire). Le domaine principal correspond au domaine de base du partenaire XMPP. Par exemple, vous pouvez entrer **fabrikam.com** comme nom de domaine du partenaire XMPP. Cette entrée est obligatoire.

6.  **Description**     La description est destinée aux notes ou à d’autres informations d’identification pour cette configuration particulière. Cette entrée est facultative.

7.  **Domaines supplémentaires**     Les domaines supplémentaires sont des domaines qui font partie du domaine de votre partenaire XMPP qui doivent être inclus dans le cadre de la communication XMPP autorisée. Par exemple, si le domaine principal est **fabrikam.com**, vous devez répertorier tous les autres domaines sous fabrikam.com que vous communiquez avec par le biais de XMPP.

8.  **Type**     de partenaire Le **type de partenaire** est un paramètre obligatoire. Vous devez choisir l’une des options suivantes pour décrire et appliquer les contacts pouvant être ajoutés. Vous pouvez sélectionner l’une des options suivantes :
    
      - **Fédéré**     Un type de partenaire **fédéré** représente un niveau élevé de confiance entre le déploiement Lync Server et le partenaire XMPP.Ce type de partenaire est recommandé pour la fédération avec des serveurs XMPP dans la même entreprise ou si une relation entre entreprises est établie.Les contacts XMPP au sein des partenaires fédérés peuvent :
        
        1.  ajouter des contacts Lync et afficher leur présence sans autorisation explicite de l’utilisateur de Lync ;
        
        2.  envoyer des messages instantanés aux contacts Lync, que l’utilisateur de Lync les ait ajoutés à leur liste des contacts ou non ;
        
        3.  afficher les notes de statut de l’utilisateur de Lync.
    
      - **Public vérifié**     Un partenaire de service **public vérifié** est un fournisseur XMPP public approuvé pour vérifier l’identité de ses utilisateurs.Les contacts XMPP dans les réseaux Public vérifié peuvent ajouter des contacts Lync, afficher la présence de ces derniers et leur envoyer des messages instantanés sans autorisation explicite des utilisateurs de Lync.Les contacts XMPP dans les réseaux Public vérifié ne peuvent jamais afficher les notes de statut des utilisateurs de Lync.Ce paramètre n’est pas recommandé.
    
      - **Public non vérifié**     Un partenaire non **vérifié public** est un fournisseur XMPP public qui n’est pas approuvé pour vérifier l’identité de ses utilisateurs.Les utilisateurs XMPP dans les réseaux Public non vérifié ne peuvent pas communiquer avec les utilisateurs de Lync sauf si l’utilisateur de Lync les a autorisés de façon explicite à les ajouter à la liste des contacts.Les utilisateurs XMPP dans les réseaux Public vérifié ne peuvent jamais afficher les notes de statut des utilisateurs de Lync.Ce paramètre est recommandé pour toutes les fédérations avec des fournisseurs XMPP publics comme Google Talk.

9.  **Type de connexion :** définit les différentes règles et paramètres de rappel.
    
      - **Négociation TLS**     Définit les règles de négociation TLS. Un service XMPP peut nécessiter TLS, peut rendre TLS facultatif ou vous pouvez décider de ne pas prendre en charge TLS. Si vous choisissez Facultatif, le service XMPP est responsable de la décision sur la négociation obligatoire. Pour afficher tous les paramètres et détails possibles pour la négociation SASL, TLS et rappel, y compris les configurations d’erreur connues et non valides-voir [paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Obligatoire**     Le service XMPP nécessite la négociation TLS.
        
          - <span></span>  
            **Facultatif**     Le service XMPP indique que TLS est obligatoire pour la négociation.
        
          - <span></span>  
            **Non pris en charge**     Le service XMPP ne prend pas en charge TLS.
    
      - **Négociation SASL**     Définit les règles de négociation SASL. Un service XMPP peut nécessiter SASL, peut rendre SASL facultatif ou vous pouvez décider de ne pas prendre en charge SASL. Si vous choisissez Facultatif, le service XMPP est responsable de la décision sur la négociation obligatoire.
        
          - <span></span>  
            **Obligatoire**     Le service XMPP requiert une négociation SASL.
        
          - <span></span>  
            **Facultatif**     Le service XMPP indique que SASL est obligatoire pour la négociation.
        
          - <span></span>  
            **Non pris en charge**     Le service XMPP ne prend pas en charge SASL.
    
      - **Prendre en charge la négociation rappel de serveur** Le processus de négociation rappel de serveur de prise en charge utilise le système DNS (Domain Name System) et un serveur faisant autorité pour vérifier que la demande provenait d’un partenaire XMPP valide. Pour ce faire, le serveur d’origine crée un message d’un type spécifique avec une clé rappel générée et recherche le serveur de réception dans le système DNS. Le serveur d’origine envoie la clé dans un flux XML à la recherche DNS résultante, vraisemblablement le serveur de réception. Lors de la réception de la clé sur le flux XML, le serveur de réception ne répond pas au serveur d’origine, mais envoie la clé à un serveur faisant autorité connu. Le serveur faisant autorité vérifie que la clé est valide ou non valide. S’il n’est pas valide, le serveur de réception ne répond pas au serveur d’origine. Si la clé est valide, le serveur de réception informe le serveur d’origine que l’identité et la clé sont valides et que la conversation peut commencer.
        
        Il existe deux états valides pour la **négociation de rappel** :
        
          - <span></span>  
            **True**     Le serveur XMPP est configuré pour utiliser la négociation rappel si une demande doit être reçue d’un serveur d’origine.
        
          - <span></span>  
            **Valeur false**     Le serveur XMPP n’est pas configuré pour utiliser la négociation rappel et si une demande doit être reçue d’un serveur d’origine, elle sera ignorée.

10. Cliquez sur **Valider** pour enregistrer vos modifications du site ou de la stratégie de l’utilisateur.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Mettre à jour des enregistrements DNS pour la passerelle XMPP de Lync Server 2013

1.  Pour configurer DNS pour la Fédération XMPP, vous devez ajouter l’enregistrement SRV suivant à votre DNS externe : \_ XMPP-Server. \_ TCP.\<domain name\> L’enregistrement SRV est résolu en un nom de domaine complet du serveur Edge d’accès, avec une valeur de port de 5269.

</div>

</div>

<span> </span>

</div>

</div>

</div>

