---
title: Configurer la passerelle XMPP sur Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5874495bb7a398ab8b5b5cde6376faaa6c193a85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Configurer la passerelle XMPP sur Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés du protocole de messagerie extensible et de présence, les stratégies s’appliquent aux utilisateurs des domaines fédérés de XMPP, mais pas aux utilisateurs de services de messagerie instantanée SIP (Session Initiation Protocol). (par exemple, Windows Live) ou domaines fédérés SIP. Vous configurez un partenaire fédéré de XMPP pour chaque domaine fédéré XMPP que vous voulez autoriser vos utilisateurs à ajouter des contacts et à communiquer avec eux. Une fois les stratégies en place, des tâches supplémentaires incluent la configuration des certificats de passerelle XMPP, le déploiement de la passerelle de Lync Server 2013 XMPP et la mise à jour des enregistrements DNS pour la passerelle XMPP.

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Configurer des certificats de passerelle XMPP sur le serveur Edge Lync Server 2013

1.  Sur le serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3: demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.
    
    <div class=" ">
    

    > [!TIP]  
    > Si vous déployez le serveur Edge pour la première fois, vous verrez exécuter au lieu de réexécuter.

    
    </div>

2.  Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.

3.  Dans la page **demande de certificat** , cliquez sur certificat de **bord externe**.

4.  Dans la page de **demande retardée ou immédiate** , activez la case à cocher **préparer la demande maintenant, puis l’envoyer plus tard** .

5.  Dans la **page fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple,\\c\_:\_CERT l’Edge. cer).

6.  Dans la page **spécifier un modèle de certificat secondaire** , pour utiliser un modèle autre que le modèle par défaut du serveur Web, activez la case à cocher utiliser un autre **modèle de certificat pour l’autorité de certification sélectionnée** .

7.  Dans la page **paramètres de nom et de sécurité** , procédez comme suit:
    
    1.  Dans **nom convivial**, tapez un nom d’affichage pour le certificat.
    
    2.  En **longueur**, spécifiez la longueur en bits (en général, la valeur par défaut 2048).
    
    3.  Vérifiez que la case à cocher **marquer le certificat en tant que clé publique en tant qu’export** est activée.

8.  Dans la page informations sur l' **organisation** , tapez le nom de l’organisation et l’unité d’organisation (par exemple, une division ou un service).

9.  Dans la page **informations géographiques** , spécifiez les informations d’emplacement.

10. Sur la page nom de l’objet **/nom** de l’objet, les informations à remplir automatiquement par l’Assistant sont affichées. Si d’autres noms d’objet sont nécessaires, vous pouvez les spécifier au cours des deux étapes suivantes.

11. Dans la page Configuration du protocole **SIP sur le nom de l’objet** , activez la case à cocher Domain pour ajouter un SIP. \<entrée\> sipdomain dans la liste noms de remplacement de l’objet.

12. Dans la page configurez d’autres **noms d’objet** , spécifiez d’autres noms d’objet obligatoires.
    
    <div class=" ">
    

    > [!TIP]  
    > Si le proxy XMPP est installé, le nom de domaine par défaut (par exemple, contoso.com) est renseigné dans les entrées du SAN. Si vous avez besoin d’entrées supplémentaires, ajoutez-les à cette étape.

    
    </div>

13. Dans la page Résumé de la **demande** , passez en revue les informations de certificat à utiliser pour générer la requête.

14. À la fin de l’exécution des commandes, vous pouvez **consulter le journal**ou cliquer sur **suivant** pour continuer.

15. Dans la page **fichier de demande de certificat** , vous pouvez afficher le fichier de demande de signature de certificat généré (CSR) en cliquant sur Afficher ou quitter l’Assistant Certificat en cliquant sur **Terminer**.

16. Copiez le fichier de demande et envoyez-le à votre autorité de certification publique.

17. Après avoir reçu, importé et attribué le certificat public, vous devez arrêter et redémarrer les services Edge Server. Pour cela, entrez dans la console de gestion de Lync Server:
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Configurer une nouvelle passerelle XMPP Lync Server 2013

1.  Ouvrez le Paneau de configuration Lync Server.

2.  Dans la barre de navigation gauche, cliquez sur **Fédération et accès externe** , puis sur **partenaires fédérés de XMPP**.

3.  Pour créer une nouvelle configuration, cliquez sur **nouveau**.

4.  Définissez les paramètres suivants:

5.  **Domaine principal (**     obligatoire). Le domaine principal est le domaine de base du partenaire XMPP. Par exemple, vous devez entrer **fabrikam.com** pour le nom de domaine de partenaire XMPP. Il s’agit d’une entrée obligatoire.

6.  **Description**   la description correspond aux notes ou autres informations d’identification pour cette configuration particulière. Cette entrée est facultative.

7.  **Domaines supplémentaires les**   domaines supplémentaires sont des domaines qui font partie du domaine de votre partenaire XMPP qui doivent être inclus dans le cadre de la communication XMPP autorisée. Par exemple, si le domaine principal est **fabrikam.com**, vous répertoriez tous les autres domaines sous fabrikam.com que vous communiquerez par le biais de la fonction XMPP.

8.  **Type**   de partenaire **** le paramètre est obligatoire. Vous devez choisir l’une des options suivantes pour décrire et mettre en œuvre les contacts qui peuvent être ajoutés. Vous pouvez sélectionner l’une des opérations suivantes:
    
      - **Fédéré** Un type de partenaire **fédéré** représente un niveau élevé de confiance entre le déploiement de Lync Server et le partenaire XMPP.Ce type de partenariat est recommandé pour la Fédération avec des serveurs XMPP au sein de la même entreprise ou pour lesquels une relation professionnelle est établie.Les contacts XMPP dans les partenaires fédérés peuvent:
        
        1.  Ajoutez des contacts Lync et consultez leur statut de présence sans autorisation expresse de l’utilisateur Lync.
        
        2.  Envoyez des messages instantanés à vos contacts Lync, que l’utilisateur de Lync les a ajoutés à leur liste de contacts ou non.
        
        3.  Afficher les notes de statut d’un utilisateur Lync.
    
      - **Vérification publique le** fournisseur **certifié public** est un fournisseur XMPP public qui est approuvé pour vérifier l’identité de ses utilisateurs.Les contacts XMPP dans les réseaux validés publics peuvent ajouter des contacts Lync et afficher leur présence et leur envoyer des messages instantanés sans autorisation expresse des utilisateurs Lync.Les contacts XMPP dans les réseaux validés publique ne voient jamais les notes d’état des utilisateurs Lync.Ce paramètre n’est pas recommandé.
    
      - **Public non vérifié** Un partenaire non **vérifié public** est un fournisseur XMPP public qui n’est pas approuvé pour vérifier l’identité de ses utilisateurs.Les utilisateurs de XMPP sur des réseaux publics non vérifiés ne peuvent pas communiquer avec des utilisateurs de Lync, sauf si l’utilisateur de Lync les a expressément autorisés en les ajoutant à la liste des contacts.Les utilisateurs de XMPP sur les réseaux publics non vérifiés ne voient jamais les notes d’état des utilisateurs Lync.Ce paramètre est recommandé pour toutes les fédérations avec les fournisseurs XMPP publics tels que Google Talk.

9.  **Type de connexion:** Définit les différentes règles et paramètres de dialback.
    
      - **La négociation**   TLS définit les règles de négociation TLS. Un service XMPP peut nécessiter le protocole TLS, peut rendre TLS facultatif ou vous définissez que TLS n’est pas pris en charge. Le choix de l’option facultative quitte le service XMPP pour une décision de demande obligatoire. Pour afficher tous les paramètres et détails possibles relatifs aux négociations SASL, TLS et Dialback, y compris les configurations d’erreur non valides et connues, voir [paramètres de négociation des partenaires fédérés de XMPP dans Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)
        
           - **Requis**   le service XMPP nécessite une négociation TLS.
        
           - **Facultatif**   le service XMPP indique que le protocole TLS est requis pour négocier.
        
           - **Non pris en charge**   le service XMPP ne prend pas en charge le protocole TLS.
    
      - **La négociation**   SASL définit les règles de négociation SASL. Un service XMPP peut être requis pour rendre SASL une option de SASL, ou vous définissez que SASL n’est pas pris en charge. Le choix facultatif pour une décision d’obligation de négociation est requis par le service XMPP du partenaire.
        
           - **Requis**   le service XMPP nécessite une négociation SASL.
        
           - **Facultatif**   le service XMPP indique que SASL est requis pour négocier.
        
           - **Non pris en charge**   le service XMPP ne prend pas en charge SASL.
    
      - **Service de support dialback Negotiation** Le processus de négociation du serveur de support dialback utilise le DNS (Domain Name System) et un serveur faisant autorité pour vérifier que la requête provient d’un partenaire XMPP valide. Pour ce faire, le serveur d’origine crée un message d’un type spécifique avec une clé dialback générée et recherche le serveur de réception dans DNS. Le serveur d’origine envoie la clé dans un flux XML à la recherche DNS résultante, le serveur de réception en principe. Dès réception de la clé via le flux XML, le serveur de réception ne répond pas au serveur d’origine, mais envoie la clé à un serveur faisant autorité connu. Le serveur faisant autorité vérifie que la clé est valide ou n’est pas valide. Si ce n’est pas le cas, le serveur de réception ne répond pas au serveur d’origine. Si la clé est valide, le serveur de réception informe le serveur d’origine qu’elle est valide et qu’elle peut commencer.
        
        Il existe deux États valides pour la **négociation Dialback**:
        
           - **True**   le serveur XMPP est configuré pour utiliser la négociation Dialback si une requête doit être reçue d’un serveur d’origine.
        
           - **False**   : le serveur XMPP n’est pas configuré pour utiliser la négociation Dialback et si une requête doit être reçue d’un serveur d’origine, il est ignoré.

10. Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie de site ou d’utilisateur.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Mettre à jour les enregistrements DNS pour Lync Server 2013 passerelle XMPP

1.  Pour configurer DNS pour la Fédération XMPP, ajoutez l’enregistrement SRV suivant à votre DNS externe:\_XMPP-Server. \_TCP. \<nom de\> domaine l’enregistrement SRV sera résolu vers le nom de domaine complet d’accès du serveur Edge, avec une valeur de port de 5269.

</div>

</div>

<span> </span>

</div>

</div>

</div>

