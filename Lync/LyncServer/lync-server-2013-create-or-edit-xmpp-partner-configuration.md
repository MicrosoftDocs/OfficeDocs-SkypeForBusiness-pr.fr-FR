---
title: 'Lync Server 2013 : créer ou modifier une configuration de partenaire XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488665bca5cd2ad1b4d2d91a3c85a6a1ddaa3916
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Créer ou modifier une configuration de partenaire XMPP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-09-03_

Microsoft Lync Server 2013 intègre un proxy XMPP (extensible Messaging and Presence Protocol) sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool frontal. Pour autoriser les connexions à partir de déploiements XMPP, vous devez configurer XMPP dans le panneau de configuration de Lync Server. Vous pouvez configurer les paramètres sur la base d’un domaine XMPP. Pour créer une association de partenariat, procédez comme suit :

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>Pour créer un nouveau partenaire fédéré ou modifier une configuration existante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **partenaires fédérés de XMPP**.

4.  Pour créer une nouvelle configuration, cliquez sur **nouveau** .

5.  Pour modifier une configuration existante, sélectionnez-la, puis cliquez sur **modifier** .

6.  Pour créer ou modifier des configurations pour les **partenaires fédérés de XMPP**, vous devez définir les paramètres suivants :

7.  **Domaine principal** (obligatoire). Le domaine principal est le domaine de base du partenaire XMPP. Par exemple, vous devez entrer **fabrikam.com** pour le nom de domaine de partenaire XMPP. Il s’agit d’une entrée obligatoire.

8.  **Description**. La description est destinée aux notes ou autres informations d’identification pour cette configuration particulière. Cette entrée est facultative.

9.  **Domaines supplémentaires**. Les domaines supplémentaires sont des domaines qui font partie du domaine de votre partenaire XMPP qui doivent être inclus dans le cadre de la communication XMPP autorisée. Par exemple, si le domaine principal est **fabrikam.com**, vous répertoriez tous les autres domaines sous fabrikam.com que vous communiquerez par le biais de la fonction XMPP. Par exemple, vous pouvez entrer **Corp.fabrikam.com** et **it.fabrikam.com** pour le domaine XMPP d’entreprise et le domaine XMPP information technologies dans le domaine XMPP principal de fabrikam. com.

10. **Type de partenaire**. Le **type de partenariat** est un paramètre requis et vous donne accès à trois options dans un menu déroulant. Vous devez choisir l’une des options suivantes pour décrire et mettre en œuvre les contacts qui peuvent être ajoutés. Vous pouvez sélectionner l’une des opérations suivantes :
    
      - **Federated**. Un type de partenaire **fédéré** est une connexion de confiance entre un serveur Lync ou un déploiement partenaire d’Office Communications Server 2007 R2.
    
      - **Public vérifié**. Un partenaire vérifié par le **public** est le moment où les contacts qui font partie d’un déploiement vérifié par le fournisseur peuvent être ajoutés à la liste des contacts de l’utilisateur. Il est possible d’envoyer des invitations à partir de l’utilisateur Lync ou de l’utilisateur de Lync.
    
      - **Public non vérifié**. Une relation **invalidée publique** implique qu’il n’y a aucun État établi et vérifiable entre les deux déploiements. Un utilisateur de Lync doit inviter le contact non vérifié à ce contact pour pouvoir l’ajouter à sa liste de contacts. Par exemple, Google GTalk n’est pas un service de XMPP vérifié publique en relation avec Lync Server. Un utilisateur GTalk ne sera pas en mesure d’ajouter l’utilisateur Lync en tant que contact, sauf s’il y a une invitation explicite envoyée par l’utilisateur Lync.

11. Remarques sur la négociation du flux et les méthodes de sécurité Transport Layer Security (TLS) et l’authentification du logiciel et de la couche de sécurité (SASL) :
    
    Les **normes** xsf (réseau de base) et l’IETF ( **Internet Engineering Task Force** ) définissent un ensemble de règles et de normes pour l’utilisation et la gestion des certificats clients TLS, des certificats de serveur TLS et du mécanisme SASL. L’utilisation de TLS et de SASL est le processus requis pour sécuriser le flux XMPP. À partir de la norme XMPP document **XEP-0178**, "spécifie un flux de protocoles recommandé pour l’utilisation du mécanisme externe SASL avec des certificats PKIX, en particulier quand un service XMPP indique que le protocole TLS est requis pour négocier.» PKIX, comme indiqué dans la documentation XSF, fait référence à l’infrastructure à clé publique (PKI).
    
    Pour plus d’informations sur les exigences XMPP, voir le document XSF XEP-0178. Pour plus d’informations, reportez-vous à la rubrique « XEP-0178 : meilleures pratiques pour l’utilisation de SASL en externe avec des certificats ». <http://xmpp.org/extensions/xep-0178.html>
    
    Reportez-vous au document IETF « extensible Messaging and Presence Protocol » (XMPP) : Core», <http://tools.ietf.org/html/rfc6120>section 5,0, négociation de STARTTLS
    
      - **Négociation TLS**. Définit les règles de négociation TLS. Un service XMPP peut nécessiter le protocole TLS, peut rendre TLS facultatif ou vous définissez que TLS n’est pas pris en charge. Le choix de l’option facultative quitte le service XMPP pour une décision de demande obligatoire. Pour afficher tous les paramètres et détails possibles relatifs aux négociations SASL, TLS et Dialback, y compris les configurations d’erreur non valides et connues, voir [paramètres de négociation des partenaires fédérés de XMPP dans Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Obligatoire**. Le service XMPP nécessite une négociation TLS.
        
          - <span></span>  
            **Facultatif**. Le service XMPP indique que TLS est requis pour négocier.
        
          - <span></span>  
            **Non pris en charge**. Le service XMPP ne prend pas en charge le protocole TLS.
    
      - **Négociation SASL**. Définit les règles de négociation SASL. Un service XMPP peut être requis pour rendre SASL une option de SASL, ou vous définissez que SASL n’est pas pris en charge. Le choix facultatif pour une décision d’obligation de négociation est requis par le service XMPP du partenaire.
        
        <div>
        

        > [!WARNING]  
        > SASL nécessite le protocole TLS. Pour utiliser SASL, TLS doit obligatoirement être requis ou facultatif. Toute configuration qui définit SASL comme étant obligatoire ou facultative doit disposer d’une prise en charge de TLS. Lorsque vous cliquez sur <STRONG>valider</STRONG> pour enregistrer vos modifications, si vous n’avez pas configuré TLS sur obligatoire ou facultatif, vous êtes averti que SASL doit prendre en charge le protocole TLS et que vos modifications ne sont pas enregistrées. Pour résoudre ce problème, définissez TLS sur <STRONG>obligatoire</STRONG> ou <STRONG>facultatif</STRONG>. Si l’utilisation de SASL est en option et si la prise en charge de la négociation TLS n’est pas possible, vous devez définir la négociation SASL sur <STRONG>non prise en charge</STRONG>. Confirmez avec le service XMPP quels sont les flux de négociation appropriés pour TLS et SASL ou le service d’interruption de service.

        
        </div>
        
          - <span></span>  
            **Obligatoire**. Le service XMPP nécessite une négociation SASL.
        
          - <span></span>  
            **Facultatif**. Le service XMPP indique que SASL est requis pour négocier.
        
          - <span></span>  
            **Non pris en charge**. Le service XMPP ne prend pas en charge SASL.
    
      - **Négociation Dialback**. Dialback négociation est définie par le fichier XSF dans document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>. Le processus de dialback serveur utilise le DNS (Domain Name System) et un serveur faisant autorité pour vérifier que la requête provient d’un partenaire XMPP valide. Pour ce faire, le serveur d’origine crée un message d’un type spécifique avec une clé dialback générée et recherche le serveur de réception dans DNS. Le serveur d’origine envoie la clé dans un flux XML à la recherche DNS résultante, le serveur de réception en principe. Dès réception de la clé via le flux XML, le serveur de réception ne répond pas au serveur d’origine, mais envoie la clé à un serveur faisant autorité connu. Le serveur faisant autorité vérifie que la clé est valide ou n’est pas valide. Si ce n’est pas le cas, le serveur de réception ne répond pas au serveur d’origine. Si la clé est valide, le serveur de réception informe le serveur d’origine qu’elle est valide et qu’elle peut commencer.
        
        Il existe deux États valides pour la **négociation Dialback**:
        
          - <span></span>  
            **True**. Le serveur XMPP est configuré pour utiliser la négociation Dialback si une requête doit être reçue d’un serveur d’origine.
        
          - <span></span>  
            **False**. Le serveur XMPP n’est pas configuré pour utiliser la négociation Dialback et, si une requête doit être reçue d’un serveur d’origine, il est ignoré.

</div>

</div>

<span> </span>

</div>

</div>

</div>

