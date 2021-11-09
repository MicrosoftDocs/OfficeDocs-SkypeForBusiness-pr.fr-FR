---
title: Configurer le service de conformité pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Résumé : Découvrez comment configurer le service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 23f28c2071063e2729deb54eea9703a7699e3e07
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858241"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurer le service de conformité pour le serveur de conversation permanente dans Skype Entreprise Server 2015

**Résumé :** Découvrez comment configurer le service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015.

La conformité de conversation permanente permet aux administrateurs de gérer une archive des messages de conversation permanente ainsi que des activités. Le service de conformité enregistre et archive les données relatives à chaque conversation de serveur de conversation permanente, y compris lorsqu’un participant :

- Rejoint une salle de conversation permanente

- Quitte une salle de conversation

- Publie un message

- Affichages de l’historique des conversation

- Charge un fichier

- Télécharge un fichier

Ces informations peuvent être récupérées à partir de la base de données de conformité SQL si nécessaire. 

> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Configurer le service de conformité à l’aide de Windows PowerShell

Une fois que le service de conformité a été activé à l’aide du Générateur de topologie, vous pouvez configurer le service à l’aide de l’cmdlet **Set-CsPersistenChatComplianceConfiguration** :

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

ou

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

Vous pouvez définir les paramètres suivants :

- AdapterType : vous permet de spécifier le type d’adaptateur. Un adaptateur est un produit tiers qui convertit les données de la base de données de conformité dans un format spécifique. XML est le XML par défaut.

- OneChatRoomPerOutputFile : ce paramètre vous permet de spécifier que des rapports distincts doivent être créés pour chaque salle de conversation.

- AddChatRoomDetails : lorsque ce paramètre est activé, il enregistre des détails supplémentaires sur chaque salle de conversation dans la base de données. Étant donné que ce paramètre peut lyser la taille de la base de données, il est désactivé par défaut.

- AddUserDetails : lorsque ce paramètre est activé, il enregistre des détails supplémentaires sur chaque utilisateur de salle de conversation dans la base de données. Étant donné que ce paramètre peut lyser la taille de la base de données, il est désactivé par défaut.

- Identité : ce paramètre autorise l’étendue des paramètres de conformité pour une collection particulière, y compris les niveaux globaux, de site et de service. La valeur par défaut est le niveau global. 

- RunInterval : ce paramètre détermine la durée avant que le serveur ne crée le fichier de sortie de conformité suivant (la valeur par défaut est 15 minutes).

## <a name="use-a-customized-compliance-adapter"></a>Utiliser un adaptateur de conformité personnalisé

Vous pouvez écrire un adaptateur personnalisé au lieu d’utiliser le XmlAdapter installé avec le serveur de conversation permanente. Pour ce faire, vous devez fournir un assembly .NET Framework contenant une classe publique qui implémente l’interface **IComplianceAdapter**. Vous devez placer cet assembly dans le dossier d’installation du serveur de conversation permanente de chaque serveur de votre pool de serveurs de conversation permanente. Chacun des serveurs de conformité peut fournir des données de conformité à votre adaptateur, mais ils ne délivrent aucun duplicata des données de conformité à plusieurs instances de votre adaptateur.

L’interface est définie dans l’assembly Compliance.dll dans l’espace de  `Microsoft.Rtc.Internal.Chat.Server.Compliance` noms. Elle définit deux méthodes que votre adaptateur personnalisé doit implémenter.

Le serveur de conformité de conversation permanente appelle la méthode suivante lors du premier chargement de l’adaptateur. Contient la configuration de conformité de conversation permanente  `AdapterConfig` qui est pertinente pour l’adaptateur de conformité :

```cpp
void SetConfig(AdapterConfig config)
```

Le serveur de conformité de conversation permanente appelle la méthode suivante à intervalles réguliers tant qu’il existe de nouvelles données à traduire. Cet intervalle de temps est égal à celui de la configuration de conformité de conversation  `RunInterval` permanente :

```cpp
void Translate(ConversationCollection conversations)
```

Contient les informations de conversation collectées à partir du dernier appel de  `ConversationCollection` cette méthode.

## <a name="customize-the-xslt-definition-file"></a>Personnaliser le fichier de définition XSLT

Les données de conformité sont livrées au format XML, que vous pouvez transformer au format le mieux adapté à votre organisation, à l’aide d’un fichier de définition XSLT. Cette rubrique décrit le fichier XML que le service de conformité crée. Elle fournit également des échantillons de fichiers de définition XSLT et de sortie.

### <a name="output-format"></a>Format de sortie

La sortie du service de conformité est classée par conversation (l’élément Conversation), puis par message (l’élément Messages), comme illustré dans l’exemple de code suivant :

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

Un élément Conversation contient quatre éléments (Channel, FirstMessage, StartTimeUTC et EndTimeUTC). L’élément Channel contient l’URI (Uniform Resource Identifier) de la salle de conversation et l’élément FirstMessage décrit le premier message de l’élément Messages. Les éléments StartTimeUTC et EndTimeUTC fournissent les heures de début et de fin de la conversation, comme illustré dans l’exemple de code suivant :

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Un élément Message contient deux éléments (Sender et DateTimeUTC) et trois attributs (Type, Content et ID). L’élément Sender représente l’utilisateur qui envoie le message, et l’élément DateTimeUTC représente lorsqu’un événement se produit, comme illustré dans l’exemple de code suivant :

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

Le tableau suivant décrit les attributs de message Type, Content et ID.

**Attributs de l’élément Messages**

|**Attribut**|**Description**|**Facultatif/Obligatoire**|
|:-----|:-----|:-----|
|Type  <br/> |Spécifie le type de message. Les types de message sont décrits dans la table Éléments de message Types de message.  <br/> |Obligatoire  <br/> |
|Contenu  <br/> |Contient le contenu du message. Les messages de type Join ou Part n’utilisent pas cet attribut.  <br/> |Facultatif  <br/> |
|ID  <br/> |Spécifie l’ID unique du contenu. Cet attribut est utilisé uniquement avec les messages de type Chat.  <br/> |Facultatif  <br/> |

Chaque élément Sender contient cinq attributs : username, ID, email, internal et URI. Ces attributs sont décrits dans la table suivante.

**Attributs de l’élément Sender**

|**Attribut**|**Description**|**Facultatif/Obligatoire**|
|:-----|:-----|:-----|
|Nom d’utilisateur  <br/> |Nom de l’expéditeur.  <br/> |Facultatif  <br/> |
|ID  <br/> |ID unique de l’expéditeur.  <br/> |Obligatoire  <br/> |
|E-mail  <br/> |Adresse e-mail de l’expéditeur.  <br/> |Facultatif  <br/> |
|Interne  <br/> |Détermine si l’utilisateur est un utilisateur interne ou fédéré. Si la valeur est Vraie, l’utilisateur est interne.  <br/> |Facultatif  <br/> |
|Uri  <br/> |URI SIP de l’utilisateur.  <br/> |Obligatoire  <br/> |

Les exemples suivants montrent les types de messages que l’élément Messages peut contenir. Elle fournit également des exemples de la manière avec laquelle chaque élément est utilisé.

Rejoindre : un utilisateur rejoint une salle de conversation.

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Partie : un utilisateur quitte une salle de conversation.

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

Conversation : adresse e-mail de l’expéditeur.

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat : un utilisateur demande du contenu à partir de l’historique de conversation.

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

Téléchargement de fichier : un utilisateur charge un fichier.

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

Téléchargement de fichier : un utilisateur télécharge un fichier.

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>XSD de sortie de conversation permanente par défaut et exemple de transformation XSL

L’exemple de code suivant contient la sortie par défaut du serveur de conformité :

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

L’exemple de code suivant contient un exemple de transformation XSL :

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
