# social-midia-app-AWSA-plify-flames
GraphQL API for Posts, Friends, and Chats
Schema (in backend/api/graphql/schema.graphql):
type Post {
 id: ID!
 content: String
 videoUrl: String
owner: String
}

type FriendRequest {
id: ID!
from: String!
to: String!
 status: String!
{

type Chat {
id: ID!
messages: [Message]
{

type Message {
content: String
from: String
{

type Query {
 getPosts: [Post]
                            getFriendRequests: [FriendRequest]
                              getChat(chatId: ID!): Chat
                              }

                              type Mutation {
                                createPost(content: String, videoUrl: String): Post
                                  sendFriendRequest(to: String!): FriendRequest
                                    respondToFriendRequest(requestId: ID!, status: String!): FriendRequest
                                      sendMessage(chatId: ID!, content: String!): Message
                                      }

                                      Resolvers are defined in backend/api/graphql/resolvers/ folder. For example, Query.getPosts.req.resolver.vtl might contain:
                            {
"version": "2018-05-29",
 "operation": "Scan",
 "table":
  {
                             "name": "Posts"


 }
                             }
